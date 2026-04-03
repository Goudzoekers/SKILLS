# Naamconventie V3 — Meta Ads ↔ Flywheel OS

Brug tussen Meta Ads Manager en Flywheel OS. Manus Bridge parser extraheert automatisch metadata.

## Structuur

| Niveau | Format | Voorbeeld |
|---|---|---|
| Campagne | `[Code] \| [Fase]_[Type]` | `RF \| Prospecting_CBO` |
| Ad Set | `[Pack] \| [Datum]` | `Pack01 \| 31032026` |
| Ad | `[Format] \| [Concept]` | `Video \| Intro` |

**Separator:** altijd ` | ` (spatie-pipe-spatie)
**Code:** 2-4 letters hoofdletters. **Fase:** Prospecting/Scaling/Retargeting/Retention. **Type:** CBO/ABO/ASC.
**Pack:** Pack01, Pack02... **Datum:** DDMMYYYY. **Format:** Video/Static/Carousel/UGC/Reel. **Concept:** vrij tekst.

## Parser → Flywheel OS

| Parsed veld | Bron |
|---|---|
| `client_code` | Campagne deel 1 |
| `funnel_stage` | Campagne deel 2 voor underscore (→ UPPERCASE) |
| `campaign_type` | Campagne deel 2 na underscore |
| `pack_id` | Ad Set deel 1 |
| `launch_date` | Ad Set deel 2 |
| `format_tag` | Ad deel 1 |
| `hook_concept` | Ad deel 2+ |

Validatie: funnel_stage EXACT PROSPECTING/SCALING/RETARGETING/RETENTION. pack_id matcht `/^Pack\d+$/i`.

## Legacy

Zonder V3-format: naam bevat "retargeting"/"remarketing" → `funnel_stage = "RETARGETING"`, rest = null.

## Migratie

```
Campagne:  "Prospecting - Royal Festival - CBO" → "RF | Prospecting_CBO"
Ad Set:    "Koud | INT | Breed | Pack01_31032026" → "Pack01 | 31032026"
Ad:        "Video_Hook1_Angle_Fear_V1" → "Video | Intro"
```

## Aggregatie (4 mini-tabellen)

| Tabel | Groepeert op | Inzicht |
|---|---|---|
| Per Fase | funnel_stage | Budget verdeling Prospecting vs Retargeting |
| Per Format | format_tag | Video vs Static vs Carousel winner |
| Per Concept | hook_concept | Welk creatief idee resoneert |
| Per Pack | pack_id | Welke batch/lancering presteert |
