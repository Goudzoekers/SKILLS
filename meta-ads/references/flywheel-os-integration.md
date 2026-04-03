# Flywheel OS Integratie — Manus Bridge API

## Architectuur

```
Meta Ads → Manus AI (extractie) → Manus Bridge API (Edge Function)
  ├── sync_ad_performance → ad_performance → auto-aggregate → metrics_weeks
  ├── sync_demographics → demographic_breakdowns
  ├── signal_alert → signals (+ Slack bij critical)
  └── inject_intelligence → hook_dna + market_intel
  → Flywheel OS Dashboard
```

Auth: `x-bridge-api-key` header = `MANUS_BRIDGE_API_KEY` env secret.

## Sync Workflow

### 1. Ad Performance
Payload: ads[] met ad_id, ad_name, ad_set_name, campaign_name, spend, impressions, clicks, link_clicks, ctr, cpc, cpm, frequency, purchases, cpa, conversion_value, roas, video_3s_views, thruplays, status, date_start, date_end.

**Auto na sync:** V3 parser → funnel_stage/pack_id/format_tag/hook_concept. Aggregatie → metrics_weeks. Slack summary. Response: `next_steps: ["sync_demographics..."]`.

### 2. Demographics
Payload: breakdowns[] met age_range, gender, day_of_week, spend, impressions, clicks, conversions, conversion_value, ctr, cpa, roas.

Flexibele veldnamen: age/age_group→age_range, sex→gender, day→day_of_week, purchases→conversions, value→conversion_value. Rijen met alle dimensies "Unknown" worden gefilterd.

### 3. Signal Alerts
Payload: signal_type (fatigue/anomaly/winner), severity (low/medium/high/critical), message, recommended_action. Slack bij critical.

## Alle Acties

**READ (10):** list_campaigns, get_campaign, get_metrics, get_execution_items, get_hook_dna, get_voice_dna, get_market_intel, get_signals, get_organic_posts, get_ad_performance

**WRITE (8+1):** sync_ad_performance, sync_demographics, inject_intelligence, trigger_graduation, refine_voice_dna, signal_alert, eindsprint_package, run_ai_engine, recalibrate_hook_weights

## Dashboard Mapping

| Tabel | Pagina |
|---|---|
| ad_performance | Ad Performance (4 mini-tabellen: Fase/Format/Concept/Pack) |
| metrics_weeks | Dashboard + Command Center (wekelijkse trend) |
| demographic_breakdowns | Demografie & Timing (leeftijd/geslacht/dag) |
| signals | Signal Center (anomalieën + acties) |
| hook_dna | Hook Genome (database + gewichten) |
| voice_dna | Voice DNA (ToV profiel) |
| market_intel | Market Intel (concurrenten) |

## Auto-Aggregatie

Na sync_ad_performance: som spend/purchases/conversion_value → 24u filter → bereken CPA/ROAS/CTR/CPC/CPM/hook_rate/hold_rate → upsert metrics_weeks (week_id per campagne+weeknr).
