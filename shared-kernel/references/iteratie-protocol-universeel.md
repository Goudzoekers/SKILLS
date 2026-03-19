# Iteratie Protocol — Data → Diagnose → Fix

Doorlopend proces NA launch. Maandelijks doorlopen per actieve klant.

## Cyclus

```
Week 1-2: Lancering → data verzamelen
Week 3: Eerste analyse → quick fixes
Week 4: Diepere analyse → structurele fixes
Maand 2+: Maandelijkse review → optimalisatie
```

## Per Module: Wat Meet Je?

### Benchmarks per Module

> **SSOT:** Alle niche-specifieke benchmarks staan in `analytics-feedback/references/benchmarks.md`.
> Raadpleeg dat bestand voor concrete drempelwaarden per metric.

### Fix-Routing per Module

| Module | Bij underperformance | Skill |
|---|---|---|
| Ads (CTR, hook rate, CPL) | Nieuwe hooks/creative | goated-ads |
| Funnel Pages (registratie CR, bounce) | Headline, formulier, laadtijd | funnel-pages |
| Webinar (show-up, retentie, pitch) | Pre-mails, content, pitch | core-story-webinar |
| E-mails (open rate, click rate) | Onderwerpregels, body, CTA | core-story-webinar |

## Diagnose-Framework

```
Stap 1: Waar in de funnel is de GROOTSTE drop-off?
Stap 2: Is het een VOLUME probleem (te weinig) of CONVERSIE probleem (te laag %)?
Stap 3: Fix van BOVEN naar BENEDEN (waterval-regel)
    → Ads fixen voor je pages fixt
    → Pages fixen voor je webinar fixt
    → Webinar fixen voor je e-mails fixt
```

**Waterval-regel:** Het heeft geen zin om een webinar te optimaliseren als er geen leads binnenkomen. Fix altijd de bovenste bottleneck eerst.

## Fix-Routing

| Bottleneck | Primaire skill | Secundaire skill |
|---|---|---|
| Te weinig impressies | Budget/targeting (buiten scope) | — |
| Lage CTR | goated-ads | — |
| Lage registratie | funnel-pages | goated-ads (congruence check) |
| Lage show-up | Lead nurture (pre-mails) | core-story-webinar |
| Lage pitch conversie | core-story-webinar | funnel-scripts |
| Lage post-webinar sales | Post-mails | funnel-pages (sales page) |

## Documentatie

Bij elke iteratie-ronde:
1. Noteer huidige metrics
2. Noteer diagnose
3. Noteer welke fix is doorgevoerd
4. Meet opnieuw na 7-14 dagen
5. Documenteer resultaat

Dit voorkomt dat je dezelfde fix twee keer probeert en bouwt een kennisbank op per klant.
