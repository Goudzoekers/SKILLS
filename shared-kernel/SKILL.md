---
name: shared-kernel
description: >
  Het fundament van het Winstarchitect skill-ecosysteem. Single Source of Truth voor gedeelde
  frameworks en protocollen. Bevat ook het Orchestratie Protocol. Trigger bij: complete acquisitie,
  onboard klant, volledige funnel, welke skill, routing, orchestratie, client brief, intake voor
  klant, start nieuw klantproject. Ook laden wanneer een content-skill gedeelde kennis nodig heeft.
---

# Shared Kernel — Single Source of Truth

Fundament onder alle content-skills. Elke gedeelde framework leeft hier — nergens anders.

## Reference Files

| Bestand | Inhoud | Laden wanneer |
|---------|--------|---------------|
| `references/pig-method.md` | P.I.G. Method: Deep Empathy, Action Beat Map, Crossroads Close | Emotionele copy, hooks, sales pages, webinars |
| `references/copywriting-principes.md` | 30 conversie-principes | ALTIJD bij copy schrijven |
| `references/niche-adaptaties.md` | B2C coaches, therapeuten, dienstverleners, e-com, SaaS | Eerste output voor een klant |
| `references/tov-kalibratie.md` | 10-parameter ToV-profiel, kalibratie-vragen | Onboarding nieuwe klant |
| `references/schrijfregels-nl.md` | Mobile-first, bullets, "zonder/zodat" | ALTIJD bij NL copy |
| `references/quality-gate.md` | 3-laags QA systeem | NA elke module, VOOR presentatie |
| `references/universal-client-brief.md` | Intake template + routing logic | Start nieuw klantproject |
| `references/golden-examples.md` | 6/10 vs 10/10 per module-type | VOOR elke module |
| `references/output-heuristieken.md` | 23 scherptests | NA eerste concept |
| `references/iteratie-protocol-universeel.md` | Feedback loop: data → diagnose → fix per module | NA launch, maandelijks |
| `references/batch-processing-protocol.md` | Meerdere klanten parallel, lifecycle, prioritering | Bij > 5 klanten actief |
| `references/lead-nurture-protocol.md` | 4 Pijlers (Availability, Speed, Personalization, Volume), ALAN data, follow-up cadans, BAMFAM | Bij lead nurture, show-up optimalisatie, follow-up sequences |
| `references/hormozi-source-map.md` | Concept → bron traceerbaarheid (GOATed Ads, Hooks, Lead Nurture, Branding, Money Models) | Bij audit, verdieping, bronverificatie |
| `references/campaign-plays.md` | 5 Revenue Play architecturen (L&L, Workshop, Top 1%, VSL, Promoreeks), Teach&Tease, evergreening, routing | Bij campagne kiezen, revenue play plannen, lijst monetiseren, quick-profit |
| `references/branding-framework.md` | Branding = pairing, 3 metrics (Reach/Influence/Direction), Branding Cycle, Boeket, 5 marktrichtingen | Bij positionering, brand-consistentie check, content-strategie |
| `references/money-model-framework.md` | 4 Offer Types, 3 Stages, Attraction/Upsell/Downsell/Continuity patronen, aanbod-sequentie design | Bij funnel-architectuur, aanbod-strategie, pricing, upsell/downsell ontwerp |

## Orchestratie Protocol

**Dependency Graph:**
```
Stap 0: Universal Client Brief (1x per klant)
Stap 1: ToV Kalibratie (1x per klant)
Stap 2: core-story-webinar → Perceptie Blueprint
Stap 3 (parallel): funnel-pages + goated-ads + funnel-scripts
Stap 4: Quality Gate op ALLE output
Stap 5: Launch → Analytics → Iteratie (doorlopend)
```

**Routing:**

| Vraag | Route |
|---|---|
| Complete acquisitie | Brief → ToV → Blueprint → Pages + Ads + Scripts |
| Ads maken | Check Brief → goated-ads |
| Webinar schrijven | Check Brief → core-story-webinar |
| Pagina maken | Check Blueprint → funnel-pages |
| Script schrijven | Check funnel → funnel-scripts |
| Ad performance | analytics-feedback |
| Feature bouwen | winst-os |
| Show rate / lead nurture / no-shows | shared-kernel → `references/lead-nurture-protocol.md` + analytics-feedback |
| Meerdere klanten | Lees batch-processing-protocol.md |
| Positionering / branding / merkstrategie | shared-kernel → `references/branding-framework.md` + relevante content-skill |
| Aanbod-structuur / upsell / downsell / pricing | shared-kernel → `references/money-model-framework.md` + funnel-pages + core-story-webinar |
| Funnel-architectuur / offer-sequentie | shared-kernel → `references/money-model-framework.md` + `funnel-pages/references/funnel-flow-map.md` |
| Campagne / revenue play / lijst monetiseren | shared-kernel → `references/campaign-plays.md` → routing naar juiste skills |

## Skill Connectie-Kaart

Elke skill heeft een duidelijke grens. Geen overlap.

```
                    shared-kernel
                   (fundament: P.I.G., ToV, schrijfregels, QA)
                         │
                         ▼
               core-story-webinar
              (strategie: Blueprint, webinar script, pitch, mails)
                    │         │
          ┌─────────┤         ├──────────┐
          ▼         ▼         ▼          ▼
     funnel-pages  goated-ads  funnel-scripts
     (pagina copy) (ads <100w) (video scripts)
          │         │          │
          └────┬────┘          │
               ▼               │
        analytics-feedback ◄───┘
        (data → diagnose → fix routing terug naar juiste skill)
```

### Eigenaarschap per Content-Type

| Content | Eigenaar | NIET in |
|---|---|---|
| Ad hooks, body, CTA (<100 woorden) | goated-ads | funnel-scripts |
| Video scripts (>100 woorden) | funnel-scripts | goated-ads |
| Pagina copy + wireframe | funnel-pages | core-story-webinar |
| Webinar presentatie-script | core-story-webinar | funnel-scripts |
| E-mail sequences | core-story-webinar | funnel-pages |
| Performance analyse | analytics-feedback | goated-ads |
| Kaleidoscoop op winners | goated-ads (maakt) + analytics-feedback (triggert) | — |
| Benchmarks & metrics | analytics-feedback | shared-kernel |
| Crossroads Close | shared-kernel (pig-method) | core-story-webinar |

### SSOT Referenties (geen duplicatie)

| Onderwerp | Leeft in (SSOT) | Andere skills verwijzen, kopiëren NIET |
|---|---|---|
| P.I.G. Method + Crossroads Close | shared-kernel/references/pig-method.md | Alle skills |
| Zonder/zodat-regel | shared-kernel/references/schrijfregels-nl.md | Alle skills |
| Verboden woorden + AI-blacklist | shared-kernel/references/tov-kalibratie.md | Alle skills |
| Alle benchmarks | analytics-feedback/references/benchmarks.md | core-story-webinar, shared-kernel |
| Registratiepagina template | funnel-pages/references/registration-page.md | core-story-webinar |
| Quality Gate (3-laags QA) | shared-kernel/references/quality-gate.md | Alle skills |
| Branding Framework (associatie-architectuur) | shared-kernel/references/branding-framework.md | Alle content-skills |
| Money Model Framework (aanbod-sequentie) | shared-kernel/references/money-model-framework.md | funnel-pages, core-story-webinar, funnel-scripts, goated-ads |
| Campaign Plays (5 revenue plays) | shared-kernel/references/campaign-plays.md | Alle content-skills |

## De Vier Wetten (universeel)

1. Systeem beslist nooit — het informeert
2. Stabiliteit > features
3. SSOT = één bron, geen duplicatie
4. Fix de bron, niet de output
