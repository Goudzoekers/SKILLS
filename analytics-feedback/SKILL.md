---
name: analytics-feedback
description: >
  Analyseer META Ads performance data en trigger creatieve optimalisatie. Sluit de cirkel
  van de Creative Flywheel: ads draaien → data komt terug → systeem optimaliseert. EXCLUSIEF
  voor ad performance analyse, funnel diagnose, en data-gedreven creative optimalisatie.
  Trigger bij: analyseer mijn ads, ad performance, welke ads schalen, funnel diagnose,
  CPL te hoog, ROAS, CTR, wat werkt, wat moet ik schalen, welke ads killen, hook rate,
  frequency, ad fatigue, creative refresh, kaleidoscoop op winners, campagne analyse,
  budget verdeling, kosten per lead, performance rapport. NIET triggeren bij: ads SCHRIJVEN
  zonder data (goated-ads), pagina's bouwen (funnel-pages), scripts (funnel-scripts),
  webinar content (core-story-webinar), technisch bouwen (winst-os).
---

# Analytics Feedback — Data-Laag van de Creative Flywheel

Sluit de cirkel: ads draaien → data → diagnose → kaleidoscoop → betere ads.

## Context Loading

> **Wet 6: Laad het minimum, niet het maximum.** Check `shared-kernel/SKILL.md` → Context Evaluation Protocol voor de decision tree. Laad alleen wat dit deliverable nodig heeft.

| Nodig | Bron | Wanneer |
|---|---|---|
| Kaleidoscoop-technieken | `goated-ads/references/creative-flywheel-methode.md` | Bij variaties op winners |
| Benchmarks per niche | `references/benchmarks.md` | Elke analyse |
| Diagnose-frameworks | `references/diagnose-matrix.md` | Elke analyse |
| Golden examples ads | `references/golden-examples-analytics.md` | Bij creative review |
| Money Model Framework | `shared-kernel/references/money-model-framework.md` | Bij funnel-diagnose: meet per Money Model stage (Stage I=CPL+CR, II=upsell take rate, III=LTV+churn) |
| Branding Framework | `shared-kernel/references/branding-framework.md` | Meet Reach (impressies), Influence (CTR, CR), Direction (sentiment, herhaalaankopen) |
| Doelgroep Mind Mining | `shared-kernel/references/doelgroep-mind-mining.md` | Bij Stap 5: verrijk klantprofiel op basis van wat converteert |

## "ANALYSEER MIJN ADS"

**Stap 1 — Data:** Vraag per ad: impressies, CTR, CPL/CPA, spend, resultaten. Ideaal ook: hook rate, frequency, leeftijd ad.

**Stap 2 — Diagnose** (zie `references/diagnose-matrix.md`):

| Signaal | Diagnose | Fix |
|---|---|---|
| CTR laag + Hook rate laag | Hook pakt niet | Nieuwe hooks → goated-ads |
| CTR laag + Hook rate hoog | Body/CTA zwak | Nieuwe body's → goated-ads |
| CTR hoog + CPL hoog | Landing page faalt | Review → funnel-pages |
| CTR hoog + CPL laag | WINNER | Schalen + kaleidoscoop |
| Frequency > 3 | Audience uitgeput | Verbreed of nieuwe creative |

**Stap 3 — Classificeer:** 🏆 Winners (top 20% → schalen), 📊 Potentials (fix 1 element), ❌ Kill (bottom 20% → uitzetten).

**Stap 4 — Rapport:** Samenvatting → Winners → Potentials → Kill → Actieplan → Kaleidoscoop-suggesties.

**Stap 5 — Doelgroep Enrichment (FEEDBACKLOOP):**
Analyseer winners en vertaal terug naar het klantprofiel (zie `doelgroep-mind-mining.md`):

| Wat converteert? | Verrijkt welk profiel-element? |
|---|---|
| Welke hook-angles winnen? | → Welke pijnpunten/verlangens zijn het sterkst (Rogue Gallery update) |
| Welke 7 Zondes-hooks presteren? | → Welke stiekeme drijfveer is dominant (7 Zondes ranking) |
| Welk awareness-niveau converteert best? | → Waar zit het gros van de doelgroep (awareness-distributie) |
| Welke sophistication-claims pakken? | → In welke fase zit de markt nu (sophistication tracking) |
| Welke emotie in body's wint? | → Welk Blair Warren-frame resoneert (dromen/falen/angst/vermoeden/vijand) |

**Output:** Naast het performance-rapport, lever een "Profiel Update" sectie: welke aannames over de doelgroep zijn bevestigd/ontkracht, en wat dit betekent voor de volgende batch hooks, het webinar script, en de sales page copy.

## "MAAK VARIATIES OP WINNERS"

Identificeer het werkende element → pas 7 kaleidoscoop-technieken toe → 7 variaties → top-3 markeren → A/B test suggestie.

## "DIAGNOSE MIJN FUNNEL"

Metrics per stap: Ad→Click (CTR >1.5%) → Registratie (CR >25%) → Show-up (>30%) → Aankoop (>5-15%). Bottleneck = grootste gap vs. benchmark. Fix van boven naar beneden (waterval-regel).

**Show-up bottleneck?** → Laad `shared-kernel/references/lead-nurture-protocol.md`. Diagnose via de 4 Pilaren:
1. Beschikbaarheid: genoeg slots? 7 dagen? Flexibele tijden?
2. Snelheid: <5 min first contact? Max 72h vooruit inplannen?
3. Personalisatie: kwalificatie? Segmentatie? Incentives? Proof?
4. Volume: genoeg follow-ups? Reminders? BAMFAM?

## "WAT MOET IK SCHALEN"

80/20 budget: 80% winners, 20% testing. Max 20-30% verhoging per 3 dagen. Kill na 5 dagen + 1000 impressies onder benchmark. Creative refresh elke 2-4 weken.

## Cross-Skill Connecties

| Diagnose uitkomst | Actie | Delegeer naar |
|---|---|---|
| Hook faalt | Nieuwe hooks schrijven | goated-ads |
| Body/CTA zwak | Body herschrijven | goated-ads |
| Landing page faalt | Pagina optimaliseren | funnel-pages |
| Show-up laag | Reminder-reeks + incentives | core-story-webinar (pre-webinar-mails) |
| Pitch faalt | Script herschrijven | core-story-webinar (pitch-opbouw) |
| Winner gevonden | Kaleidoscoop variaties | goated-ads (creative-flywheel-methode) |
| Stage I underperforms (CPL, CR) | Attraction Offer herzien | shared-kernel/references/money-model-framework.md → 5 Attraction Patronen |
| Stage II underperforms (upsell take rate) | Upsell/Downsell herzien | shared-kernel/references/money-model-framework.md → Upsell + Downsell Patronen |
| Stage III underperforms (churn, LTV) | Continuity Offer herzien | shared-kernel/references/money-model-framework.md → 3 Continuity Patronen |
| Brand metrics dalen (Influence/Direction) | Brand-consistentie audit | shared-kernel/references/branding-framework.md → Boeket check |
| Campagne-type performance evalueren | Meet per play-type (L&L→leads, Workshop→ticket+upsell, Top1%→high-ticket CR, VSL→view rate+CR, Promo→email CR) | shared-kernel/references/campaign-plays.md |
| Doelgroep profiel verrijken | Stap 5 output → update awareness/sophistication/7 Zondes/Rogue Gallery | shared-kernel/references/doelgroep-mind-mining.md |
| Ad-namen decoderen (format, hook, angle) | Lees naamconventie voor patroonherkenning in data | ad-naamconventie/references/conventie-compleet.md |

## Quality Gate

Data-gebaseerd, niet aannames. Min. 1000 impressies per ad. Niche-specifieke benchmarks (zie `references/benchmarks.md`). Concreet actieplan (welke skill, welke actie). Schaal-advies incrementeel. Profiel Update sectie aanwezig met concrete verrijkingen.
