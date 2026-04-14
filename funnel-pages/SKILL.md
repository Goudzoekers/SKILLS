---
name: funnel-pages
description: >
  Ontwerp funnel pagina's als copy + wireframe in .docx. EXCLUSIEF voor pagina-ontwerp:
  registratie, opt-in, upsell, VIP upgrade, thank you, downsell, sales page, order bump,
  checkout. Trigger bij: maak een pagina, landing page, registratiepagina, sales page copy,
  opt-in pagina, upsell schrijven, thank you page, funnel architectuur, pagina-ontwerp,
  acquisitie-architectuur. NIET triggeren bij: advertentieteksten (goated-ads), video scripts
  (funnel-scripts), webinar presentatie-scripts (core-story-webinar), e-mails.
---

# Acquisitie-Architectuur — Pagina Engine

Copy + wireframe structuur voor funnel-pagina's. Primair B2C coaches/therapeuten.

## Context Loading

> **Wet 6: Laad het minimum, niet het maximum.** Check `shared-kernel/SKILL.md` → Context Evaluation Protocol → Reference Loading per Deliverable voor de exacte PRIMARY/SECONDARY/SKIP per paginatype.

| Nodig | Bron | Wanneer |
|---|---|---|
| **ToV-profiel + signature patronen + anti-taal** | **`shared-kernel/references/tov-kalibratie.md` + Client Brief** | **ALTIJD. Laden VÓÓR schrijven. Niet-onderhandelbaar.** |
| Schrijfregels NL | `shared-kernel/references/schrijfregels-nl.md` | ALTIJD bij NL copy (niet-onderhandelbaar) |
| Conversie-principes | `shared-kernel/references/copywriting-principes.md` | Opt-in, sales page, registratie. SKIP bij thank you page (prospect is al geconverteerd). |
| Quality Gate | `shared-kernel/references/quality-gate.md` | NA elke pagina |
| Conversie-patronen | `references/conversie-patronen.md` | PRIMARY bij opt-in (2-Step, Anti-List), thank you (Old/New), sales page (Niet-voor-jou, Prijs van Falen). Per paginatype: check welke patronen relevant zijn. |
| Headline Frameworks | `references/headline-frameworks.md` | Bij opt-in en registratiepagina headlines. SKIP bij thank you, checkout. |
| ICP Filter Framework | `shared-kernel/references/icp-filter-framework.md` | Sales pages: alle 5 pijlers. Opt-in: pijler 1+3. Thank you: pijler 1 (licht). Checkout: SKIP. Check decision tree in het framework. |
| P.I.G. storytelling | `shared-kernel/references/pig-method.md` | Sales pages, opt-in (hero). SKIP bij thank you (al verwerkt), upsell (ander doel), checkout. |
| Doelgroep Mind Mining | `shared-kernel/references/doelgroep-mind-mining.md` | Opt-in headline (awareness), sales page probleem-sectie (Rogue Gallery). SKIP bij thank you, checkout. |
| Breakthrough Advertising | `shared-kernel/references/breakthrough-advertising.md` | Sales pages: alle 7 technieken. SKIP bij opt-in (te zwaar), thank you, checkout, upsell (kort). |
| Positionering Frameworks | `shared-kernel/references/positionering-frameworks.md` | Sales page "Over Jou" sectie. SKIP bij opt-in (geen ruimte), thank you, checkout. |
| Money Model Framework | `shared-kernel/references/money-model-framework.md` | Bij funnel-architectuur, upsell/downsell ontwerp. SKIP bij losse pagina's. |
| Branding Framework | `shared-kernel/references/branding-framework.md` | SKIP tenzij brand-consistentie check gevraagd. |
| Niche-aanpassingen | `shared-kernel/references/niche-adaptaties.md` | Eerste pagina per klant. Daarna: alleen als niche-specifieke termen nodig zijn. |

**Eigen references per paginatype:** `references/registration-page.md`, `references/upsell-page.md`, `references/thankyou-page.md`, `references/downsell-page.md`, `references/sales-page.md`, `references/funnel-flow-map.md`, `references/video-guidelines.md`, `references/conversie-patronen.md`, `references/headline-frameworks.md`

**Video scripts:** delegeer naar funnel-scripts. video-guidelines.md = briefing-spec.

**Check eerst:** Is er een Client Brief + ToV-profiel? Ja → laad het ToV-profiel (10 parameters + signature patronen + anti-taal + alter ego routing). Nee → verzamel input via `shared-kernel/references/universal-client-brief.md` + kalibreer via `tov-kalibratie.md`.

## Configuraties

- **A:** Webinar (registratie → upsell → thank you/downsell → sales page)
- **B:** Product Launch (sales page → checkout → thank you)
- **C:** Lead Magnet (registratie → upsell → thank you/downsell)
- **D:** High-Ticket (registratie → sales page → premium thank you)
- **E:** Simpel (registratie → thank you)
- **F:** VSL-First (landing page + ungated video + CTA naar call)

B2C coaches: Config A of C. Therapeuten: Config E of D. High-ticket met sceptische doelgroep: Config F.

## Booking Component (Thank You / CTA pagina's)

Bij high-ticket funnels (Config C, D, F) met call-booking als conversie:
- **Aanbevolen:** iClosed 2-Step Scheduler (inline embed). Lead capture VÓÓR kalender, disqualificatie-vragen als ICP Filter, native Meta Pixel. Zie tracking-architectuur Fase 2 Route A.
- **Legacy:** Calendly embed of link. Beperkingen: geen lead capture bij drop-off, geen disqualificatie, fragiele Zapier-keten voor attributie.
- CTA-copy boven embed moet verlangen opbouwen + Kryptonite: "Niet iedereen komt door de vragen heen. Dat is de bedoeling."
- Bevestigingspagina altijd op eigen domein (geen redirect naar extern platform).

## Per Sectie Opleveren

1. **[WIREFRAME]** — Layout, kleuren, media, responsief
2. **[COPY]** — Volledig uitgeschreven tekst
3. **[NOTITIE]** — Implementatie-tips (optioneel)

## Output

.docx via docx-skill. Bestandsnaam: `[klantnaam]-[paginatype]-acquisitie-architectuur.docx`. Complete architectuur: elke pagina apart.

## A/B Test Workflow

Vraag ALTIJD: headline, subtekst, of paginalengte? Schrijf twee versies waarbij ALLEEN dat element verschilt.

## Cross-Skill Connecties

| Nodig van andere skill | Bron |
|---|---|
| Headline + belofte voor registratiepagina | core-story-webinar → Perceptie Blueprint |
| Video scripts voor pagina-secties | funnel-scripts → schrijft het script, dit levert de briefing |
| Ad-belofte voor congruence check | goated-ads → winnende ad hook |
| Benchmarks voor pagina-conversie | analytics-feedback/references/benchmarks.md |
| Zonder/zodat-regel | shared-kernel/references/schrijfregels-nl.md |
| P.I.G. voor sales pages | shared-kernel/references/pig-method.md |
| Offer-type per pagina (Attraction/Upsell/Downsell) | shared-kernel/references/money-model-framework.md |
| Brand-consistentie (pagina = merk-ervaring) | shared-kernel/references/branding-framework.md |
| Campagne-type bepaalt paginatype (L&L=registratie, Workshop=mini-salespage, VSL=video-page) | shared-kernel/references/campaign-plays.md |

## Sales Page Enrichment (bij sales-page.md)

**Headline Alignment op Market Awareness + Sophistication** (zie `doelgroep-mind-mining.md`):
- Probleembewust → headline raakt het probleem, laat pijn voelen
- Oplossingsbewust → headline toont verlangen + differentieert
- Productbewust → uniek mechanisme + "zonder [bezwaar]"
- Compleet bewust → de deal (prijs, urgentie, exclusiviteit)
- Sophistication fase 5 → identiteit verkopen

**Sectie-specifieke verrijkingen:**
- Probleem-sectie: gebruik Rogue Gallery angles (angst, boosheid, frustratie, onzekerheid)
- Over Jou: status dripping + Kryptonite Marketing (zwakte→kracht)
- Uniek Mechanisme: Defy the Norms (positioneer tegen marktnorm) + Mechanization (reason-why, HOE tot in detail) + Concentration (5 wegen naar superioriteit)
- Dromen-sectie: 7 Zondes als extra lens + Intensification (picture words, visuele taal) + Identification (rolverkoop: welke rol krijgt de klant?)
- Praktische Zaken: Redefinition (versimpel, stapel voordelen, herkader prijs)
- Volledige paginastructuur: Gradualization (begin bij geaccepteerde overtuiging, bouw stap voor stap naar koopbeslissing)
- Algehele toon: Camouflage (lees als artikel/verhaal, niet als verkooppagina)

**Belief Installation Check:** Loop NA het schrijven alle secties na: welke foute overtuigingen zijn geadresseerd? Welke ontbreken? Vul aan.

## Quality Gate

Doorloop `shared-kernel/references/quality-gate.md`. Aanvullend: mobile-first check, geen verbindingstekens, max 3 zinnen per alinea, zonder/zodat-regel toegepast (zie schrijfregels-nl.md), bullets max 8 woorden, CTA 3x herhaald, prijsanker correct, P.I.G. bij sales pages.
