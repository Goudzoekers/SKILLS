# Campaign Architectuur — META Ads voor Coaches & Therapeuten

## Inhoudsopgave
1. Fundamenten: Hormozi Ad Assembly × M3 Method
2. Campagne Setup Stap-voor-Stap
3. Targeting Strategie
4. Budget Allocatie Model
5. Lead Form Ads Setup
6. Funnel Integratie
7. Retargeting Architectuur
8. Advantage+ Configuratie

---

## 1. Fundamenten

### Hormozi Ad Assembly Process
Bron: $100M GOATed Ads Playbook

Ads worden GEASSEMBLEERD, niet gecreëerd. Het process:
- 50 hooks × 3-5 meats × 1-3 CTAs = 150-750 ads per week
- 80% preptime → hooks, 20% → meat, ~0% → CTAs
- Hook bronnen: eigen winners, eigen content, andermans ads, andermans content, ad libraries

### Moonlighters M3 Method
Bron: The Moonlighters Paid Advertising Assets Library

3-fase optimalisatie framework:
- **M1 — Messaging:** Copy, creative, offer alignment
- **M2 — Mechanism:** Targeting, plaatsing, funnel flow
- **M3 — Metrics:** Data-driven iteratie, scaling rules

Gemiddeld resultaat: 43% ROAS verbetering binnen 90 dagen.

### Integratie: Assembly × M3

| Hormozi Component | M3 Fase | Winstarchitect Skill |
|---|---|---|
| Hook schrijven | M1 (Messaging) | goated-ads |
| Campagne setup | M2 (Mechanism) | meta-ads (deze) |
| Performance analyse | M3 (Metrics) | analytics-feedback |

---

## 2. Campagne Setup Stap-voor-Stap

### Pre-launch Checklist
1. Meta Business Suite account → correct bedrijf gekoppeld
2. Ad Account aanmaken (1 per partner, niet delen)
3. Meta Pixel installeren op ALLE funnel pagina's
4. Conversions API (CAPI) server-side koppelen
5. Custom conversie-events definiëren:
   - `Lead` = formulier ingevuld
   - `Schedule` = afspraak ingepland
   - `Purchase` = verkoop
6. Payment method koppelen
7. Business verification voltooien

### Campaign Naming Convention
Format: `[Laag] - [Doelgroep] - [Objectief] - [Datum]`

Voorbeelden:
- `COLD - Ouders 25-45 - Leads - 2026-04`
- `WARM - VideoViewers 50% - Conversie - 2026-04`
- `HOT - FormAbandoners 7d - Conversie - 2026-04`

### Ad Set Naming Convention
Format: `[Targeting] - [Plaatsing] - [Budget]`

### Ad Naming Convention (Flywheel OS)
Zie ad-naamconventie skill: `[Format] - [Hook] - [Angle] - [Variant]`

---

## 3. Targeting Strategie

### Cold Prospecting

**Advantage+ Audience (aanbevolen 2025-2026):**
- Laat Meta's AI het werk doen
- Geef "suggesties" via Audience Suggestions (niet restricties)
- Breed: 18-65+, land-niveau
- Meta optimaliseert op basis van je conversie-event

**Interest Stacking (handmatig als backup):**
- Max 3-5 interesses per ad set
- Coaches-niche: persoonlijke ontwikkeling, mindfulness, coaching, Tony Robbins, etc.
- Therapeuten-niche: psychologie, zelfhulp, therapie, GGZ, burnout, etc.
- Opvoedcoaches: ouderschap, opvoeding, kind & gezin, etc.

**Lookalike Audiences:**
- Bron: bestaande klanten (e-maillijst upload)
- Start met 1% (meest gelijkend)
- Schaal naar 2% en 5% bij volume
- Minimaal 100 broncontacten nodig

### Warm Retargeting

Custom Audiences opbouwen:
- Video viewers (25%, 50%, 75%, 95%) — laatste 30 dagen
- Website bezoekers — laatste 14 dagen
- Instagram/Facebook engagers — laatste 30 dagen
- Lead form openers die NIET submitten — laatste 7 dagen

### Hot Remarketing

- Registranten die niet kwamen opdagen
- Winkelwagen/checkout verlaters
- Qualified leads die niet boekten
- Venster: 1-7 dagen (urgentie)

### Exclusies (KRITISCH — voorkomt budget verspilling)
- Bestaande klanten/kopers → altijd excluden in cold
- Mensen die al geconverteerd zijn → excluden in retargeting
- Medewerkers/team → excluden overal

---

## 4. Budget Allocatie Model

### Break-Even CPL Berekening

```
Break-Even CPL = (Gemiddelde klantwaarde × Close rate × Show rate) / Gewenste ROAS

Voorbeeld:
- Klantwaarde: €2.000
- Close rate: 20%
- Show rate: 60%
- Gewenste ROAS: 3x

Break-Even CPL = (€2.000 × 0.20 × 0.60) / 3 = €80 per lead
```

### Startbudget Advies

| Partner Fase | Dagbudget | Maandbudget |
|---|---|---|
| Startend (validatie) | €30-50 | €900-1.500 |
| Groeiend (optimalisatie) | €50-150 | €1.500-4.500 |
| Scaling (versnelling) | €150-500+ | €4.500-15.000+ |

### Verdeling Over Lagen

Gebruik de Moonlighters Ad Spend Calculator logica:
- Cold: 60-70% (hoofdmotor)
- Warm: 20-30% (conversie-accelerator)
- Hot: 5-10% (opruimen)

---

## 5. Lead Form Ads Setup

Specifiek voor coaches/therapeuten die geen website/funnel hebben:

### Meta Instant Forms
- Higher Intent form type (filtert tire-kickers)
- Velden: Voornaam, Email, Telefoon + 1 kwalificatievraag
- Kwalificatievraag voorbeeld: "Wat is je grootste uitdaging op dit moment?"
- Privacy policy link verplicht (kan Google Doc zijn)
- Thank you screen: volgende stap helder communiceren

### CRM Integratie
- Zapier/Make koppeling naar CRM binnen 5 minuten
- Automatische welkomst-mail/SMS direct na submit
- Lead scoring op basis van kwalificatievraag

---

## 6. Funnel Integratie

### Webinar Funnel (meest gebruikt bij Winstarchitect)
```
Ad → Registratiepagina → Thank You + Scheduler → Webinar → Sales Call → Close
     (funnel-pages)   (meta-ads nurture)    (core-story)  (CLOSER)
```

### Lead Magnet Funnel
```
Ad → Opt-in pagina → Thank You + Nurture → Sales Call → Close
     (funnel-pages)  (meta-ads nurture)     (CLOSER)
```

### Direct Application Funnel (high-ticket)
```
Ad → Application Form → Qualify → Sales Call → Close
     (lead form ad)      (meta-ads nurture)  (CLOSER)
```

---

## 7. Retargeting Architectuur

### 3-Staps Retargeting Cascade

**Stap 1 (Dag 1-3 na engagement):**
- Proof-driven creative: testimonial, case study
- Boodschap: "Kijk wat [naam] bereikte..."

**Stap 2 (Dag 4-7):**
- Objection-busting creative
- Boodschap: "De #1 reden waarom mensen twijfelen..."

**Stap 3 (Dag 8-14):**
- Urgentie/schaarste creative
- Boodschap: "Laatste plekken / deadline nadert"

### Retargeting Creative Regels
- Nooit dezelfde ad als in cold
- Specifiek refereren aan eerdere actie ("Je hebt onze video gezien...")
- Frequentie cap: max 3x per week per persoon

---

## 8. Advantage+ Configuratie (2025-2026)

### Advantage+ Leads Campaigns
- Meta's AI optimaliseert automatisch targeting, plaatsing, creative
- Lever 3-5 verschillende creatives aan (Meta test ze)
- Gebruik breed publiek (geen restricties)
- Optimaliseer voor downstream events (niet alleen leads, maar qualified leads)

### Advantage+ Creative
- Laat Meta automatisch aanpassen: tekst variaties, achtergrondkleuren, cropping
- Lever assets aan in meerdere formaten (1:1, 4:5, 9:16)

### Wanneer NIET Advantage+ gebruiken
- Bij zeer kleine budgetten (< €30/dag) → te weinig data voor AI
- Bij zeer niche doelgroepen (< 50.000 mensen) → handmatig targeten
- Bij compliance-gevoelige niches (therapeuten) → meer controle nodig
