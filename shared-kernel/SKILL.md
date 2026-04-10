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
| `references/tov-kalibratie.md` | 10-parameter ToV-profiel, kalibratie-vragen, 9 stemtypes (Blackman/Woodcock) | Onboarding nieuwe klant |
| `references/schrijfregels-nl.md` | Mobile-first, bullets, "zonder/zodat" | ALTIJD bij NL copy |
| `references/quality-gate.md` | 3-laags QA systeem | NA elke module, VOOR presentatie |
| `references/universal-client-brief.md` | Intake template + routing logic | Start nieuw klantproject |
| `references/golden-examples.md` | 6/10 vs 10/10 per module-type | VOOR elke module |
| `references/output-heuristieken.md` | 30 scherptests (incl. Intensification, 7 Zondes, Belief, Sophistication, Kryptonite, Identification, Camouflage) | NA eerste concept |
| `references/iteratie-protocol-universeel.md` | Feedback loop: data → diagnose → fix per module | NA launch, maandelijks |
| `references/batch-processing-protocol.md` | Meerdere klanten parallel, lifecycle, prioritering | Bij > 5 klanten actief |
| `references/lead-nurture-protocol.md` | 4 Pijlers (Availability, Speed, Personalization, Volume), ALAN data, follow-up cadans, BAMFAM | Bij lead nurture, show-up optimalisatie, follow-up sequences |
| `references/hormozi-source-map.md` | Concept → bron traceerbaarheid (GOATed Ads, Hooks, Lead Nurture, Branding, Money Models) | Bij audit, verdieping, bronverificatie |
| `references/campaign-plays.md` | 5 Revenue Play architecturen (L&L, Workshop, Top 1%, VSL, Promoreeks), Teach&Tease, evergreening, routing | Bij campagne kiezen, revenue play plannen, lijst monetiseren, quick-profit |
| `references/branding-framework.md` | Branding = pairing, 3 metrics (Reach/Influence/Direction), Branding Cycle, Boeket, 5 marktrichtingen | Bij positionering, brand-consistentie check, content-strategie |
| `references/money-model-framework.md` | 4 Offer Types, 3 Stages, Attraction/Upsell/Downsell/Continuity patronen, aanbod-sequentie design | Bij funnel-architectuur, aanbod-strategie, pricing, upsell/downsell ontwerp |
| `references/doelgroep-mind-mining.md` | 7 Zondes (verborgen verlangens), Rogue Gallery (7 emotiecategorieën), Blair Warren (5 overtuigingsframes), Market Awareness (5 niveaus), Market Sophistication (5 fasen), Belief Mapping | Bij intake, hook-generatie, angle-mining, headline-keuze, webinar blueprint, elke content-skill |
| `references/positionering-frameworks.md` | Alter Ego (3 thema's), Kryptonite Marketing, Defy the Norms, Status & Autoriteit (10 tactieken), Thought Leadership, Filosofie-manifest, Infotainment Formula, 9 Stemtypes | Bij personal brand, ToV, webinar positionering, sales page "Over Jou", content-strategie |
| `references/breakthrough-advertising.md` | 7 Schwartz persuasion-technieken: Intensification (beeldscherpte), Identification (rolverkoop), Gradualization (overtuigingstrap), Redefinition (bezwaar-herkadering), Mechanization (HOE onthullen), Concentration (competitieve superioriteit), Camouflage (vermomde verkoop) | Bij sales pages, webinar scripts, VSL, e-mail sequences, elke lange-vorm copy |
| `references/closer-sales-call.md` | CLOSER Framework: Clarify→Label→Overview→Sell vacation→Explain concerns→Reinforce decision. Setting/closing script voor 1-op-1 sales calls, setter/closer rolsplitsing | Bij funnel met call-stap, sales call scripts, setter/closer briefing |
| `references/icp-filter-framework.md` | 5-pijler ICP selectiestructuur: Belofte, Mechanisme, Identiteit (Type A/B), Prijs van Falen, Gedragsvereiste. Graaf-vragen, 6/10 vs 10/10, samenvat-format, context-afhankelijke toepassing per skill | NA client brief bij nieuwe klant. Bij positioneringsvraag. Bij funnel die niet converteert. NIET bij puur technische taken of analytics-only. |

## Orchestratie Protocol

### Context Evaluation (ALTIJD EERST)

Voordat je iets laadt, routeert, of produceert — doorloop deze 4 vragen:

```
VRAAG 1: Wat is de taak?
├── Content produceren (copy, ads, scripts, pagina's) → Ga naar vraag 2
├── Strategie bepalen (positionering, ICP, Blueprint) → Laad shared-kernel frameworks
├── Data analyseren (performance, metrics) → analytics-feedback, GEEN content-skills
├── Technisch bouwen (component, feature, bug) → winst-os, GEEN shared-kernel
└── Klantcommunicatie (bericht, update, onboarding) → partner-comms, GEEN frameworks

VRAAG 2: Wat weet ik al?
├── Client Brief + ICP Filter + ToV bestaan → Gebruik ze. Laad NIET opnieuw.
├── Client Brief bestaat, ICP Filter niet → Maak eerst het ICP Filter (Stap 0b).
├── Niets bestaat → Start bij Stap 0 (Client Brief).
└── Klant is al live, er is data → Start bij analytics-feedback.

VRAAG 3: Wat is het MINIMUM dat ik moet laden?
├── Schrijfregels NL + ToV = ALTIJD bij Nederlandse copy (niet-onderhandelbaar)
├── Elk deliverable heeft een PRIMARY reference (zie tabel hieronder)
├── Shared-kernel frameworks = alleen laden als het deliverable ze NODIG heeft
└── "Alle content-skills" in SSOT = onwaar. Check per geval.

VRAAG 4: Welk diepte-niveau?
├── Quick (1 deliverable, klant is bekend) → Primary reference + schrijfregels
├── Standard (nieuw deliverable-type voor bekende klant) → Primary + 1-2 frameworks
└── Deep (nieuw klantproject of strategische herdefinitie) → Full stack
```

### Reference Loading per Deliverable

Niet "laad alles." Laad het MINIMUM dat 10/10 output produceert.

**Kolom-legenda:**
- **PRIMARY:** Altijd laden. Zonder dit geen output.
- **SECONDARY:** Laden als het deliverable die laag nodig heeft. Check per geval.
- **SKIP:** Niet laden tenzij expliciet gevraagd.

| Deliverable | PRIMARY | SECONDARY (als nodig) | SKIP |
|---|---|---|---|
| **Opt-in pagina** | schrijfregels, registration-page.md, conversie-patronen.md, ICP filter (pijler 1+3) | headline-frameworks, breakthrough-advertising (Gradualization) | campaign-plays, money-model, closer-sales-call, branding-framework |
| **Sales page** | schrijfregels, sales-page.md, ICP filter (alle 5), pig-method, breakthrough-advertising | doelgroep-mind-mining, positionering-frameworks | campaign-plays, lead-nurture, dm-outreach |
| **Thank you page** | schrijfregels, thankyou-page.md, conversie-patronen.md (Old/New, Video Testimonials) | ICP filter (pijler 1 belofte) | pig-method (al verwerkt op opt-in), campaign-plays, money-model |
| **Ad batch** | schrijfregels, creative-flywheel-methode, hook-library, golden-examples-ads | doelgroep-mind-mining (7 Zondes, Rogue Gallery), ICP filter (pijler 3+4 als angle-bron) | sales-page.md, registration-page.md, campaign-plays, lead-nurture |
| **VSL script** | schrijfregels, video-guidelines.md, pig-method, ICP filter (alle 5) | breakthrough-advertising, doelgroep-mind-mining | registration-page.md, hook-library, campaign-plays |
| **Webinar Blueprint** | doelgroep-mind-mining, pig-method, ICP filter (alle 5), copywriting-principes | positionering-frameworks, breakthrough-advertising, money-model | registration-page.md, hook-library, dm-outreach |
| **Webinar script** | Blueprint (al gemaakt), schrijfregels | breakthrough-advertising (Intensification, Camouflage) | pig-method (zit in Blueprint), ICP filter (zit in Blueprint) |
| **E-mail sequence** | schrijfregels, campaign-plays (welke play?), lead-nurture-protocol | doelgroep-mind-mining (awareness per mail) | sales-page.md, video-guidelines, branding-framework |
| **Campagne setup** | campaign-architectuur.md, meta-platform-updates.md, ad-naamconventie | benchmarks.md | Alle shared-kernel content-frameworks |
| **Performance analyse** | benchmarks.md, analytics-feedback SKILL.md | Geen | Alle content-skills, alle shared-kernel frameworks |
| **Kickstart Call script** | closer-sales-call.md, ICP filter (pijler 3+5) | Geen | Alle content-skills |
| **Partner bericht** | partner-comms templates | Geen | Alles |

### Anti-Patronen (wat je NIET doet)

1. **"Laad alles voor de zekerheid"** — Nee. Elke reference die je laadt zonder reden verdunt de focus. Meer context ≠ betere output.
2. **"Breakthrough Advertising bij elke batch ads"** — Nee. Schwartz is voor lange-vorm copy (sales pages, VSL, webinar). Niet voor 3-zins ad hooks.
3. **"Doelgroep Mind Mining bij een thank you page"** — Nee. De prospect is al geconverteerd. Mind Mining is voor ACQUISITIE-copy.
4. **"ICP Filter bij een bug fix"** — Nee. Technische taken gebruiken geen content-frameworks.
5. **"P.I.G. Method bij e-mail #7 in een nurture sequence"** — Nee. P.I.G. is voor de eerste touchpoints. Na 6 mails is de relatie al gebouwd.
6. **"Money Model bij een enkele ad"** — Nee. Money Model is voor funnel-ARCHITECTUUR, niet voor losse deliverables.

### Wanneer WEL de volle stack laden

Er zijn 3 situaties waarin je ALLES laadt:

1. **Nieuw klantproject (Stap 0-3):** Client Brief → ICP Filter → ToV → Blueprint → alles. Dit is de enige keer dat de volle stack gerechtvaardigd is.
2. **Strategische herdefinitie:** De positionering klopt niet, de funnel converteert niet, de klant wil een andere richting. Dan herstart je bij ICP Filter en laad je alles opnieuw.
3. **Quality Gate faalt herhaaldelijk:** Als output steeds door de Quality Gate zakt, is er een dieper probleem. Herlaad de relevante frameworks en check of de input (Brief, ICP, ToV) klopt.

In alle andere gevallen: laad het minimum. Produceer. Check met Quality Gate. Klaar.

**Dependency Graph:**
```
Stap 0: Universal Client Brief (1x per klant)
  └→ Incl. Doelgroep Mind Mining: 7 Zondes, Rogue Gallery, awareness/sophistication, belief mapping
Stap 0b: ICP Filter (1x per klant, NA client brief)
  └→ 5 pijlers: Belofte, Mechanisme, Identiteit (Type A/B), Prijs van Falen, Gedragsvereiste
  └→ Voedt ALLE volgende stappen. Zonder ICP filter = 6/10 output.
Stap 1: ToV Kalibratie (1x per klant)
  └→ Incl. 9 stemtypes + alter ego profiel + positionering
Stap 2: core-story-webinar → Perceptie Blueprint
Stap 3 (parallel): funnel-pages + goated-ads + funnel-scripts
Stap 4: Quality Gate op ALLE output
Stap 5: Launch → Analytics → Iteratie (doorlopend)
  └→ FEEDBACKLOOP: analytics-feedback → verrijk Mind Mining profiel → hervalideer Blueprint
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
| Campagne opzetten / targeting / budget / Advantage+ / pixel | meta-ads |
| Ad namen / naamconventie / hernoemen | ad-naamconventie |
| Feature bouwen | winst-os |
| Show rate / lead nurture / no-shows | shared-kernel → `references/lead-nurture-protocol.md` + analytics-feedback |
| Meerdere klanten | Lees batch-processing-protocol.md |
| Positionering / branding / merkstrategie | shared-kernel → `references/branding-framework.md` + relevante content-skill |
| Aanbod-structuur / upsell / downsell / pricing | shared-kernel → `references/money-model-framework.md` + funnel-pages + core-story-webinar |
| Funnel-architectuur / offer-sequentie | shared-kernel → `references/money-model-framework.md` + `funnel-pages/references/funnel-flow-map.md` |
| Campagne / revenue play / lijst monetiseren | shared-kernel → `references/campaign-plays.md` → routing naar juiste skills |
| Hook-angles / emotionele triggers | shared-kernel → `references/doelgroep-mind-mining.md` → 7 Zondes + Rogue Gallery |
| Positionering / personal brand / alter ego | shared-kernel → `references/positionering-frameworks.md` + `references/branding-framework.md` |
| Market awareness / sophistication bepalen | shared-kernel → `references/doelgroep-mind-mining.md` → awareness + sophistication matrix |
| Klant update / onboarding / weekly pulse / milestone | partner-comms |
| Sales call script / setting / closing | shared-kernel → `references/closer-sales-call.md` + funnel-scripts (prep video) |
| Multi-angle funnel schalen | shared-kernel → `references/campaign-plays.md` (Multi-Angle Ecosystem) + funnel-pages → `references/conversie-patronen.md` |
| DM outreach / organische acquisitie | goated-ads → `references/dm-outreach-frameworks.md` |
| Headline A/B testing / formules | funnel-pages → `references/headline-frameworks.md` |
| ICP definitie / ideale klant / filter / selectie / Type A/B | shared-kernel → `references/icp-filter-framework.md` |
| Prijs van falen / kosten van niets doen / urgentie | shared-kernel → `references/icp-filter-framework.md` (pijler 4) + funnel-pages → `references/conversie-patronen.md` (copy-sectie) |
| "Niet voor jou" / afstoting / gedragsvereiste | shared-kernel → `references/icp-filter-framework.md` (pijler 5) + funnel-pages → `references/conversie-patronen.md` (patroon) |

## Skill Connectie-Kaart

Elke skill heeft een duidelijke grens. Geen overlap.

```
                    shared-kernel
                   (fundament: P.I.G., ToV, schrijfregels, QA, lead-nurture, campaign-plays)
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
          │         ▼          │
          │    ► meta-ads ◄────┘
          │    (campagne setup, targeting, budget,
          │     retargeting, scaling, Advantage+)
          │         │    │
          │         ▼    ▼
          │    ad-naamconventie
          │    (namen standaardiseren)
          └────┬────┘
               ▼
        analytics-feedback ◄── meta-ads levert data-structuur
        (data → diagnose → fix routing terug naar juiste skill)

     partner-comms (parallel aan elke stap — onboarding, milestones, weekly pulse)
     winst-os (technisch platform + orchestratie hub)
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
| Campagne-architectuur, targeting, budget, pixel/CAPI | meta-ads | goated-ads, analytics-feedback |
| Lead form ads configuratie + retargeting structuur | meta-ads | funnel-pages |
| Kaleidoscoop op winners | goated-ads (maakt) + analytics-feedback (triggert) | — |
| Benchmarks & metrics | analytics-feedback | shared-kernel |
| Crossroads Close | shared-kernel (pig-method) | core-story-webinar |
| Ad-naamgeving (format, hook, angle codes) | ad-naamconventie | goated-ads, analytics-feedback |
| Klantcommunicatie (onboarding, updates, escalatie) | partner-comms | alle andere skills |
| Sales call scripts (setting/closing) | shared-kernel (closer-sales-call) | funnel-scripts |

### SSOT Referenties (geen duplicatie)

| Onderwerp | Leeft in (SSOT) | Wie laadt wanneer |
|---|---|---|
| P.I.G. Method + Crossroads Close | shared-kernel/references/pig-method.md | funnel-pages (sales page, opt-in), funnel-scripts (VSL, video), core-story-webinar (Blueprint). NIET: ads <100w, thank you pages, e-mails na mail 3, technische taken. |
| Zonder/zodat-regel | shared-kernel/references/schrijfregels-nl.md | ALTIJD bij Nederlandse copy. Niet-onderhandelbaar. |
| Verboden woorden + AI-blacklist | shared-kernel/references/tov-kalibratie.md | ALTIJD bij Nederlandse copy. Niet-onderhandelbaar. |
| Alle benchmarks | analytics-feedback/references/benchmarks.md | analytics-feedback (primair), core-story-webinar (webinar KPI's). NIET: content-productie. |
| Registratiepagina template | funnel-pages/references/registration-page.md | funnel-pages (registratie). core-story-webinar verwijst, kopieert niet. |
| Quality Gate (3-laags QA) | shared-kernel/references/quality-gate.md | NA elke output. Altijd. |
| Branding Framework (associatie-architectuur) | shared-kernel/references/branding-framework.md | Bij positioneringsvraag, brand-consistentie check. NIET bij losse ads, e-mails, technische taken. |
| Money Model Framework (aanbod-sequentie) | shared-kernel/references/money-model-framework.md | Bij funnel-architectuur, offer-design, upsell/downsell. NIET bij losse pagina's, ads, scripts. |
| Campaign Plays (5 revenue plays) | shared-kernel/references/campaign-plays.md | Bij campagne kiezen, revenue play plannen, lijst monetiseren. NIET bij content-productie. |
| Doelgroep Mind Mining (7 Zondes, Rogue Gallery, awareness/sophistication, beliefs) | shared-kernel/references/doelgroep-mind-mining.md | goated-ads (hook-angles), funnel-pages (headline, bullets), core-story-webinar (Blueprint). NIET bij thank you pages, e-mails na mail 3, technische taken. |
| Positionering Frameworks (Alter Ego, Kryptonite, Status, 9 Stemtypes) | shared-kernel/references/positionering-frameworks.md | Bij positioneringsvraag, personal brand, sales page "Over Jou". NIET bij losse ads, e-mail sequences, checkout pages. |
| Breakthrough Advertising (7 Schwartz technieken) | shared-kernel/references/breakthrough-advertising.md | Lange-vorm copy: sales pages, VSL, webinar scripts. NIET bij ads <100w, e-mails, registratiepagina's, thank you pages. |
| Ad-naamconventie (format, hook, angle codes) | ad-naamconventie/references/conventie-compleet.md | goated-ads (output), analytics-feedback (data-matching), meta-ads (campaign setup). |
| META Ads campagne-architectuur | meta-ads/references/campaign-architectuur.md | meta-ads alleen. |
| Meta platform updates | meta-ads/references/meta-platform-updates.md | meta-ads alleen. |
| Top 10 YouTube bronnen | meta-ads/references/top-10-bronnen.md | meta-ads alleen. |
| Partner Comms templates | partner-comms/references/templates.md | partner-comms alleen. |
| CLOSER Sales Call Framework | shared-kernel/references/closer-sales-call.md | Bij sales call scripts, setter/closer briefing. funnel-scripts bij prep video. NIET bij content-productie. |
| Conversie-patronen (Config F, 2-Step, Anti-List, Old/New, Niet-voor-jou, Prijs van Falen, Video Testimonials, Multi-Angle) | funnel-pages/references/conversie-patronen.md | funnel-pages (structuur-elementen per paginatype). goated-ads (Niet-voor-jou als hook). NIET bij scripts, e-mails, webinar content. |
| Headline Frameworks (10 formules) | funnel-pages/references/headline-frameworks.md | funnel-pages (headline A/B), goated-ads (headline-inspiratie). NIET bij scripts, webinar, e-mails. |
| DM Outreach Frameworks (4 patronen) | goated-ads/references/dm-outreach-frameworks.md | goated-ads (organisch), meta-ads (integratie met paid). |
| ICP Filter Framework (5-pijler selectiestructuur) | shared-kernel/references/icp-filter-framework.md | Stap 0b bij nieuwe klant. Bevat eigen decision tree: welke pijlers per deliverable. NIET bij technische taken, analytics-only, partner-comms (tenzij call-kwalificatie). |

## De Zes Wetten (universeel)

1. Systeem beslist nooit — het informeert
2. Stabiliteit > features
3. SSOT = één bron, geen duplicatie
4. Fix de bron, niet de output
5. Geen output zonder feedbackloop — elke module meet, elke meting verrijkt het klantprofiel
6. **Laad het minimum, niet het maximum** — meer context ≠ betere output. Elke reference die je laadt zonder reden verdunt de focus. Check de Context Evaluation boven de routing.
