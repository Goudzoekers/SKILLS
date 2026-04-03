---
name: meta-ads
description: >
  Volledig META Ads campagnemanagement voor B2C coaches, therapeuten en kennisondernemers.
  EXCLUSIEF voor: campagne-architectuur, targeting, budgetverdeling, Advantage+ setup,
  lead form ads, retargeting structuur, pixel/CAPI setup, scaling protocol, en campagne-
  optimalisatie. Integreert Hormozi Awareness-model, Moonlighters M3 Method, en platform-
  specifieke best practices 2025-2026. Trigger bij: campagne opzetten, Meta Ads Manager,
  targeting strategie, budget verdelen, Advantage+, campagne structuur, scaling ads, CPL
  verlagen, ROAS verhogen, retargeting, lookalike audiences, lead form ads, campagne setup,
  ad account structuur, funnel ads, webinar ads campagne, pixel installeren, CAPI setup,
  cold traffic, warm traffic, hot remarketing. NIET triggeren bij: ad COPY schrijven
  (goated-ads), ad performance ANALYSE (analytics-feedback), funnel pagina's bouwen
  (funnel-pages), video scripts (funnel-scripts), webinar CONTENT (core-story-webinar),
  lead nurture SEQUENCES (shared-kernel → lead-nurture-protocol.md), revenue play kiezen
  (shared-kernel → campaign-plays.md).
---

# META Ads Campagne Engine

Technische campagne-architectuur voor Winstarchitect-partners. Van pixel tot scaling.

## Positie in het Ecosysteem

```
                shared-kernel
               (fundament + lead-nurture-protocol + campaign-plays)
                     │
                     ▼
           core-story-webinar
          (strategie: Blueprint)
                │         │
      ┌─────────┤         ├──────────┐
      ▼         ▼         ▼          ▼
 funnel-pages  goated-ads  funnel-scripts
 (pagina copy) (ad copy)   (video scripts)
      │         │          │
      │         ▼          │
      │    ► meta-ads ◄────┘     ← DEZE SKILL
      │    (campagne setup,       (ontvangt copy van goated-ads,
      │     targeting, budget,     scripts van funnel-scripts,
      │     retargeting, scaling)  pagina's van funnel-pages)
      │         │    │
      │         ▼    ▼
      │    ad-naamconventie
      └────┬────┘
           ▼
    analytics-feedback
    (data → diagnose → fix routing)
```

## Scherpe Afbakening

| Vraag | Skill | NIET meta-ads |
|---|---|---|
| "Zet een campagne op" | **meta-ads** | — |
| "Schrijf ad copy/hooks" | goated-ads | Geen copy schrijven |
| "Analyseer mijn ads" | analytics-feedback | Geen data-analyse |
| "Hoe verbeter ik show rate?" | shared-kernel → lead-nurture-protocol | Geen nurture sequences |
| "Welke revenue play gebruiken?" | shared-kernel → campaign-plays | Geen play-selectie |
| "Bouw een registratiepagina" | funnel-pages | Geen pagina's bouwen |
| "Hernoem mijn ads" | ad-naamconventie | Geen naamgeving |

## Context Loading

| Nodig | Bron | Wanneer |
|---|---|---|
| META-specifieke setup + targeting + budget | `references/campaign-architectuur.md` | ALTIJD |
| Top 10 YouTube experts + bronnen | `references/top-10-bronnen.md` | Bij research, inspiratie, partner educatie |
| Meta platform updates 2025-2026 | `references/meta-platform-updates.md` | Bij Advantage+, nieuwe features, compliance |
| Lead Nurture (4 Pijlers, ALAN) | `shared-kernel/references/lead-nurture-protocol.md` | Bij show rate optimalisatie (**SSOT = shared-kernel**) |
| Campaign Plays (5 revenue types) | `shared-kernel/references/campaign-plays.md` | Bij campagne-type selectie (**SSOT = shared-kernel**) |
| Awareness + Sophistication | `shared-kernel/references/doelgroep-mind-mining.md` | Bij targeting-strategie |
| Niche-aanpassingen | `shared-kernel/references/niche-adaptaties.md` | Eerste campagne per partner |
| Client Brief | `shared-kernel/references/universal-client-brief.md` | Start nieuw project |
| Quality Gate | `shared-kernel/references/quality-gate.md` | NA elke campagne-opzet |
| Benchmarks | `analytics-feedback/references/benchmarks.md` | Bij KPI-bepaling |

## Campagne Architectuur — 3 Lagen

```
Laag 1: COLD PROSPECTING (60-70% budget)
  └→ Doelgroep: Problem Aware + Solution Aware
  └→ Objectief: Leads / Conversies
  └→ Creative: via goated-ads skill
  └→ Targeting: Broad + Advantage+ Audience

Laag 2: WARM RETARGETING (20-30% budget)
  └→ Doelgroep: Engaged (video viewers, page visitors, form starters)
  └→ Objectief: Conversies
  └→ Creative: Proof-driven, testimonials, parade of proof
  └→ Targeting: Custom Audiences 1-30 dagen

Laag 3: HOT REMARKETING (5-10% budget)
  └→ Doelgroep: Abandoners, registranten die niet kwamen
  └→ Objectief: Conversies
  └→ Creative: Urgentie, countdown, personal message
  └→ Targeting: Custom Audiences 1-7 dagen
```

## "ZET CAMPAGNE OP" Delivery

Bij een campagneverzoek, lever:

1. **Technische Setup Checklist:** Pixel, CAPI, conversie-events, payment, verification
2. **3-Laags Campagne Architectuur:** Per laag: objectief, targeting, budget %, plaatsing
3. **Targeting Plan:** Advantage+ config, interests, custom audiences, lookalikes, exclusies
4. **Budget Calculator:** Dagbudget per laag, break-even CPL, scaling triggers
5. **Retargeting Cascade:** 3-staps (proof → objection-bust → urgentie), timing, frequency caps
6. **Creative Brief → Route naar goated-ads:** Aantal hooks (50), body's (5), CTAs (3), awareness-niveaus, formats
7. **Lead Nurture Activatie → Route naar shared-kernel:** Verwijs partner naar lead-nurture-protocol

## Scaling Protocol

### Wanneer schalen?
- CPA < break-even 3 dagen achtereen
- Frequency < 2.5
- CTR (link) > 1%
- Hook rate (3-sec views / impressies) > 25%

### Hoe schalen?
1. **Horizontaal:** Dupliceer winnende ad set → nieuw publiek
2. **Verticaal:** Verhoog budget 20% per 3 dagen (niet >20% ineens)
3. **Kaleidoscoop:** Nieuwe hooks op winnende meat+CTA (trigger goated-ads)
4. **Platform-split:** Reels, Stories, Feed apart testen

### Kill Criteria
- CPA > 2x break-even na 1.000 impressies → pauzeer
- CTR < 0.5% na 48 uur → ververs creative
- Frequency > 3.5 zonder conversies → nieuw publiek

## Compliance (Coaches & Therapeuten)

- Geen medische claims (therapeuten!)
- Geen before/after die fysieke/mentale verandering impliceert
- Geen persoonlijke targeting op gezondheid ("Heb jij last van angst?")
- Altijd disclaimer bij resultaatclaims
- Privacy policy verplicht bij lead forms
- Special Ad Categories checken (housing, social, health)

## Quality Gate

Na campagne-opzet, controleer:
1. ☐ Pixel + CAPI geïnstalleerd en geverifieerd?
2. ☐ Custom conversie-events correct?
3. ☐ 3-laags structuur compleet (cold/warm/hot)?
4. ☐ Budget binnen break-even marge?
5. ☐ Lead nurture actief? (→ check shared-kernel/lead-nurture-protocol)
6. ☐ Exclusies correct (geen budget verspilling)?
7. ☐ Compliance check (restricted content)?
8. ☐ Creative brief naar goated-ads gerouteerd?
9. ☐ Naamconventie via ad-naamconventie skill?
10. ☐ Analytics dashboard ingericht? (→ analytics-feedback kan meten)
11. ☐ Scaling triggers gedefinieerd?

## Eigenaarschap

| Content-Type | Eigenaar | meta-ads rol |
|---|---|---|
| Campagne-structuur, targeting, budget | **meta-ads** | Eigenaar |
| Pixel/CAPI technische setup | **meta-ads** | Eigenaar |
| Lead form ads configuratie | **meta-ads** | Eigenaar |
| Retargeting architectuur | **meta-ads** | Eigenaar |
| Scaling beslissingen | **meta-ads** + analytics-feedback | Eigenaar (structuur) + data (trigger) |
| Ad copy (hooks, body, CTA) | goated-ads | Ontvangt brief van meta-ads |
| Ad namen | ad-naamconventie | meta-ads routeert |
| Lead nurture sequences | shared-kernel | meta-ads verwijst |
| Campaign play selectie | shared-kernel | meta-ads implementeert |
| Performance analyse | analytics-feedback | meta-ads levert data-structuur |
