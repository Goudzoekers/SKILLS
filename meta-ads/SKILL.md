---
name: meta-ads
description: >
  META Ads campagnemanagement voor B2C coaches, therapeuten, kennisondernemers.
  EXCLUSIEF: campagne-architectuur, targeting, budget, Advantage+, lead form ads,
  retargeting, pixel/CAPI, scaling, naamconventie V3, Flywheel OS sync via Manus Bridge.
  Trigger bij: campagne opzetten, Meta Ads Manager, targeting, budget, Advantage+,
  scaling ads, CPL/ROAS, retargeting, lookalike, lead form ads, pixel, CAPI, cold/warm/hot,
  naamconventie, ad naming, data sync, Manus Bridge.
  NIET: ad copy (goated-ads), analyse (analytics-feedback), pagina's (funnel-pages),
  scripts (funnel-scripts), webinar (core-story-webinar), nurture sequences (shared-kernel),
  revenue plays (shared-kernel).
---

# META Ads Campagne Engine

## Ecosysteem Positie

```
shared-kernel (lead-nurture + campaign-plays)
    ↓
core-story-webinar (Blueprint)
    ↓
funnel-pages + goated-ads + funnel-scripts
    ↓
► meta-ads ← (campagne setup, targeting, budget, retargeting, scaling)
    ↓           ↓
ad-naamconventie   Flywheel OS (Lovable) ← Manus Bridge API (18 acties)
    ↓
analytics-feedback (data → diagnose)
```

## Afbakening

| Vraag | Route |
|---|---|
| Campagne opzetten | **meta-ads** |
| Ad copy/hooks | goated-ads |
| Ad analyse | analytics-feedback |
| Show rate/nurture | shared-kernel → lead-nurture-protocol |
| Revenue play | shared-kernel → campaign-plays |
| Ads hernoemen | V3 naamconventie hieronder |
| GTM / consent / CAPI / sGTM / tracking audit | tracking-architectuur |
| Data sync dashboard | meta-ads → Manus Bridge |

## Context Loading

> **Wet 6: Laad het minimum, niet het maximum.** Check `shared-kernel/SKILL.md` → Context Evaluation Protocol voor de decision tree. Laad alleen wat dit deliverable nodig heeft.

| Bron | Wanneer |
|---|---|
| `references/campaign-architectuur.md` | ALTIJD |
| `references/naming-convention-v3.md` | Ads hernoemen, sync, Manus Bridge |
| `references/flywheel-os-integration.md` | Data sync, dashboard, signals |
| `references/ssot-resoluties.md` | SSOT-gaps, ticket_sales, winner-definitie, fatigue, pacing |
| `references/top-10-bronnen.md` | Research, partner educatie |
| `references/meta-platform-updates.md` | Advantage+, compliance |
| `shared-kernel/references/lead-nurture-protocol.md` | Show rate (SSOT) |
| `shared-kernel/references/campaign-plays.md` | Play-selectie (SSOT) |
| `shared-kernel/references/doelgroep-mind-mining.md` | Targeting |
| `shared-kernel/references/sophistication-playbook.md` | Campagne-messaging: check Meta Ads cold + retargeting tabellen per fase. Fase bepaalt hook-strategie (fase 5 = identiteit, fase 3 = mechanisme). Fase × Awareness matrix bepaalt welke targeting → welke messaging. |
| `shared-kernel/references/icp-filter-framework.md` | Cold traffic: Identiteit (pijler 3) + Prijs van Falen (pijler 4) zijn de sterkste angles in fase 4-5. Retargeting: Gedragsvereiste (pijler 5) als confrontatie-CTA. |

## 3-Laags Architectuur

| Laag | Budget | Doelgroep | V3 Naam | Sophistication-Strategie |
|---|---|---|---|---|
| COLD | 60-70% | Problem/Solution Aware | `[Klant] \| Prospecting_CBO` | Messaging volgt sophistication-fase: fase 3 = mechanisme-hook, fase 5 = identiteits-hook. Check `sophistication-playbook.md` → Meta Ads cold tabel. |
| WARM | 20-30% | Video viewers, engagers | `[Klant] \| Retargeting_CBO` | Retargeting = altijd awareness 4-5. Focus op bewijs, identiteit, urgentie. Check retargeting-tabel. |
| HOT | 5-10% | Abandoners, no-shows | `[Klant] \| Retention_CBO` | Confrontatie: Crossroads Close, Prijs van Falen. "Je hebt de video gezien. Wat ga je doen?" |

## V3 Naamconventie (SSOT)

Flywheel OS parseert automatisch via Manus Bridge:

| Niveau | Format | Voorbeeld | Parsed |
|---|---|---|---|
| Campagne | `[Code] \| [Fase]_[Type]` | `RF \| Prospecting_CBO` | client_code, funnel_stage, campaign_type |
| Ad Set | `[Pack] \| [Datum]` | `Pack01 \| 31032026` | pack_id, launch_date |
| Ad | `[Format] \| [Concept]` | `Video \| Intro` | format_tag, hook_concept |

Separator altijd ` | `. Fase: Prospecting/Scaling/Retargeting/Retention. Format: Video/Static/Carousel/UGC/Reel. Legacy zonder V3 → auto-detectie op "retargeting"/"remarketing".

## Delivery bij "ZET CAMPAGNE OP"

1. Technische Setup: Pixel, CAPI, events, payment, verification
2. 3-Laags Architectuur: objectief, targeting, budget %, plaatsing per laag
3. V3 Naamconventie: exacte namen campagne/ad set/ad
4. Targeting Plan: Advantage+, interests, customs, lookalikes, exclusies
5. Budget Calculator: dagbudget/laag, break-even CPL, scaling triggers
6. Retargeting Cascade: proof→objection-bust→urgentie + timing
7. Creative Brief → goated-ads: 50 hooks, 5 body's, 3 CTAs
8. Lead Nurture → shared-kernel: lead-nurture-protocol
9. Flywheel OS Sync: Manus Bridge instructie

## Scaling

**Schaal:** CPA < break-even 3d | Freq < 2.5 | CTR > 1% | Hook rate > 25%
**Hoe:** Horizontaal (nieuwe Pack) → Verticaal (+20%/3d) → Kaleidoscoop (nieuw Concept) → Platform-split
**Kill:** CPA > 2× na 1000 impr | CTR < 0.5% na 48u | Freq > 3.5

## Compliance (Therapeuten)

Geen medische claims. Geen before/after. Geen targeting op gezondheid. Disclaimer verplicht. Privacy policy bij lead forms. Special Ad Categories checken.

## Quality Gate

☐ Pixel+CAPI ☐ Events correct ☐ 3 lagen compleet ☐ Budget < break-even ☐ Nurture actief (shared-kernel) ☐ Exclusies correct ☐ Compliance OK ☐ Creative brief → goated-ads ☐ V3 naamconventie correct ☐ Analytics dashboard → analytics-feedback ☐ Scaling triggers ☐ Flywheel OS campagne aangemaakt ☐ UTM-tracking
