# SSOT Resoluties — Flywheel OS Data-Integriteit

Audit response op 10 geïdentificeerde SSOT-gaps. Per issue: diagnose, SSOT-definitie, implementatie.

---

## 🔴 #1: SimpleTicket UTM-conversies (PRIORITEIT)

**Probleem:** Meta-attributie (ad_performance.purchases) en SimpleTicket (werkelijke verkoop) zijn twee bronnen van waarheid.

**SSOT-definitie:** `ticket_sales` is de SSOT voor werkelijke omzet. `ad_performance` is SSOT voor Meta-gerapporteerde attributie. Beide bestaan naast elkaar, met een expliciete `attribution_gap` metric.

### Tabel: `ticket_sales`

```sql
create table ticket_sales (
  id uuid primary key default gen_random_uuid(),
  campaign_id uuid references campaigns(id) not null,
  sale_date date not null,
  source text not null,              -- 'simpleticket', 'mollie', 'stripe'
  utm_source text,                   -- 'facebook', 'instagram', 'organic'
  utm_medium text,                   -- 'cpc', 'social', 'email'
  utm_campaign text,                 -- V3 campagnenaam (parseable)
  utm_content text,                  -- ad-level identifier
  tickets_sold integer not null default 0,
  revenue numeric(10,2) not null default 0,
  ticket_type text,                  -- 'early_bird', 'regular', 'vip'
  -- parsed velden (auto via trigger)
  funnel_stage text,                 -- parsed uit utm_campaign
  client_code text,                  -- parsed uit utm_campaign
  created_at timestamptz default now(),
  updated_at timestamptz default now()
);
```

### Bridge Action: `sync_ticket_sales`

```json
{
  "action": "sync_ticket_sales",
  "campaign_id": "uuid",
  "payload": {
    "sales": [
      {
        "sale_date": "2026-04-01",
        "source": "simpleticket",
        "utm_source": "facebook",
        "utm_campaign": "RF | Prospecting_CBO",
        "tickets_sold": 12,
        "revenue": 588.00,
        "ticket_type": "regular"
      }
    ]
  }
}
```

**Auto na sync:** V3 parser op utm_campaign → funnel_stage + client_code. Aggregatie naar `metrics_weeks` als `actual_revenue` naast `meta_conversion_value`. Dashboard toont `attribution_gap = meta_conversion_value - actual_revenue`.

### UTM-structuur voor SimpleTicket

```
?utm_source=facebook
&utm_medium=cpc
&utm_campaign=RF|Prospecting_CBO     ← V3 parseable
&utm_content=Video|Intro              ← ad-level
```

---

## 🔴 #2: SSOT-definitie "winner"

**Probleem:** `execution_items.verdict`, `imported_creatives.is_winner`, `ad_performance.roas` geven elk een ander antwoord.

**SSOT-definitie:**

| Veld | Betekenis | Wanneer |
|---|---|---|
| `ad_performance.roas` | Data-waarheid. Objectief. | ALTIJD leidend voor scaling/kill beslissingen |
| `execution_items.verdict` | Operationele status (active/paused/graduated) | Status in workflow |
| `imported_creatives.is_winner` | Historisch label na graduation | Archief/inspiratie |

**Regel:** Een ad is een "winner" als: `roas >= 2.0 AND spend >= €50 AND frequency < 3.0` gedurende minimaal 3 dagen. Dit is de ENIGE definitie. Edge function `evaluate-winner` past dit toe en zet `execution_items.verdict = 'graduated'` + `imported_creatives.is_winner = true` automatisch.

---

## 🔴 #3: Daily pacing vs wekelijkse aggregatie

**Probleem:** Geen daily pacing SSOT voor budget-alerts in eindsprint (laatste 10-14 dagen).

**SSOT-definitie:** Voeg `daily_pacing` view toe op `ad_performance`.

```sql
create view daily_pacing as
select
  campaign_id,
  date_start as pacing_date,
  sum(spend) as daily_spend,
  sum(purchases) as daily_purchases,
  case when sum(spend) > 0
    then sum(conversion_value) / sum(spend)
    else 0 end as daily_roas,
  sum(impressions) as daily_impressions
from ad_performance
group by campaign_id, date_start;
```

**Signal trigger:** Als `daily_spend` > `planned_daily_budget * 1.2` OF `daily_roas < 1.0` voor 2+ opeenvolgende dagen → auto `signal_alert` met severity=high.

---

## 🔴 #4: Fatigue definitie

**Probleem:** Drie plekken, drie logica's.

**SSOT-definitie:** Eén threshold, overal:

```
Ad is FATIGUED wanneer:
  frequency >= 3.5
  AND (ctr_week_n < ctr_week_n-1 * 0.7)   -- CTR daalde 30%+
  AND impressions >= 1000
```

Leeft als constante in edge function `evaluate-fatigue`. Schrijft naar `execution_items.fatigued_at` (datum) + `signals` (alert). Geen andere code mag fatigue bepalen.

---

## 🟡 #5: Conversie-waarde eigenaarschap

**SSOT-definitie:**

| Bron | Tabel | Geldt als |
|---|---|---|
| Meta Pixel | `ad_performance.conversion_value` | Geattribueerde waarde (platform-perspectief) |
| SimpleTicket/Mollie | `ticket_sales.revenue` | Werkelijke omzet (bank-perspectief) |
| Handmatig | `organic_conversions.revenue` | Niet-geattribueerde organische verkoop |

**Dashboard:** Toont alle drie naast elkaar. `true_roas = ticket_sales.revenue / ad_performance.spend`. Dit is de metric die scaling-beslissingen stuurt bij events met ticketverkoop.

---

## 🟡 #6: campaign_snapshots niet gebruikt

**Fix:** `aggregate-metrics-week` edge function schrijft na elke aggregatie een snapshot:

```sql
insert into campaign_snapshots (campaign_id, snapshot_date, metrics_json)
values (campaign_id, now(), row_to_json(metrics_weeks.*));
```

Snapshot wordt dagelijks gemaakt. Week-over-week vergelijking = `snapshot[week_n] - snapshot[week_n-1]`.

---

## 🟡 #7: Frequency cap SSOT

**SSOT-definitie:** Campagne-level frequency = gewogen gemiddelde van alle actieve ads:

```
campaign_frequency = SUM(ad.frequency * ad.impressions) / SUM(ad.impressions)
```

Berekend in `daily_pacing` view. Alert als `campaign_frequency >= 3.0` in retargeting/retention laag.

---

## 🟢 #8: Wie mag data muteren — audit trail

**Regel:** Elke write naar `ad_performance`, `ticket_sales`, `metrics_weeks` logt:

| Veld | Waarde |
|---|---|
| `mutation_source` | 'manus_bridge' / 'csv_import' / 'manual_ui' |
| `mutated_by` | user_id of 'system' |
| `mutated_at` | timestamptz |

**Conflict resolution:** Last-write-wins MET `mutation_source` prioriteit: manus_bridge > csv_import > manual_ui. Bij conflict: signal_alert met severity=medium.

---

## 🟢 #9: Week-definitie

**SSOT-definitie:** `week_number` in `metrics_weeks` = **campagne-relatieve week** (week 1 = eerste 7 dagen na campagne-start). Niet ISO-week, niet kalenderweek.

```
week_number = CEIL((current_date - campaign.start_date + 1) / 7)
```

Dashboard label: "Week 3 (14-20 apr)".

---

## 🟢 #10: Cross-campaign learning

**SSOT-tabel:** `campaign_learnings` (nieuw)

```sql
create table campaign_learnings (
  id uuid primary key default gen_random_uuid(),
  campaign_id uuid references campaigns(id),
  learning_type text,       -- 'hook_winner', 'audience_insight', 'timing', 'creative_format'
  description text,
  evidence jsonb,           -- {roas: 4.2, spend: 500, hook_concept: "FOMO"}
  applicable_niches text[], -- ['events', 'coaching']
  created_at timestamptz default now()
);
```

Na campagne-afsluiting: `analytics-feedback` skill genereert learnings → insert via bridge action `archive_learnings`. Volgend jaar: query `campaign_learnings WHERE 'events' = ANY(applicable_niches)`.
