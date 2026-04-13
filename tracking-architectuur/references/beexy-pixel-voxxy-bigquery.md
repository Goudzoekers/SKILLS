# Beexy Pixel + Voxxy Partnership + BigQuery

Voxxy Creative Lab is de technische partner voor alle tracking-implementaties. Jerry Bierenbroodspot (CTO) doet de techniek. Winstarchitect doet de commercie en klantrelatie. Bij tracking-gesprekken met klanten gaan we samen het gesprek in: Winstarchitect legt uit WAAROM, Voxxy legt uit HOE.

## Partnerverdeling

| Domein | Wie | Wat |
|---|---|---|
| Commercie + strategie | Winstarchitect (Rick) | Klantgesprek, uitleg waarom, waardepropositie, upsell naar Fase 2/3 |
| Techniek + implementatie | Voxxy Creative Lab (Jerry) | GTM, consent, scripts, sGTM, CAPI, Beexy Pixel, BigQuery |
| Gezamenlijk | Beiden om tafel met klant | Architectuurvoorstel, toezegging klant in scope, toekomstpad uitleggen |

**Contactgegevens Voxxy:** hello@voxxycreativelab.com — Jerry Bierenbroodspot, CTO

## 3-Niveau Verkoopstrategie

Bij elk klantgesprek over tracking, bouw je het laag voor laag op. Elk niveau is zelfstandig waardevol. Je verkoopt niet alles tegelijk — je laat zien waar ze staan en waar ze naartoe kunnen.

### Niveau 1: Lead-Optimalisatie (wat nu draait na Fase 1)

**Wat de klant krijgt:**
- AVG-conforme tracking (cookiebanner, consent mode v2)
- Meta Pixel die wél data stuurt, maar alleen na toestemming
- Lead-event met Advanced Matching (e-mail, telefoon, voornaam)
- Campagnes kunnen draaien op Lead-optimalisatie

**Wat je de klant vertelt:**
"Je kunt nu adverteren zonder juridisch risico. Meta ontvangt schone conversiedata. Dit is het fundament."

**Beperking om eerlijk te benoemen:**
"Je optimaliseert nu op formulierinzendingen. Maar een lead is niet hetzelfde als een boeking of een klant. We meten nog niet wat echt telt."

### Niveau 2: Boeking-Optimalisatie (Calendly + Zapier + Airtable)

**Wat de klant krijgt:**
- fbclid stroomt door naar Calendly-boeking via UTM-rewriting
- Zapier legt fbclid vast in Airtable
- Meta CAPI ontvangt boeking-events (niet alleen leads)
- Meta kan optimaliseren op daadwerkelijke boekingen

**Wat je de klant vertelt:**
"We meten nu niet alleen wie het formulier invulde, maar wie er daadwerkelijk een gesprek boekte. Dat is een fundamenteel ander optimalisatiesignaal."

**Beperkingen om eerlijk te benoemen:**
- Calendly is een gesloten systeem — geen eigen tracking, beperkte integratie
- Zapier is fragiel — als een stap faalt, valt de keten weg
- Safari (25% NL) beperkt cookies tot 24 uur bij ads-verkeer — fbclid kan verloren gaan
- Ad blockers (~20% NL) blokkeren fbclid-capture volledig
- "Dit niveau heeft een plafond. En dat plafond ligt bij de tools."

### Niveau 3: Volledige Attributie (Beexy Pixel + sGTM + BigQuery)

**Wat de klant krijgt:**
- Beexy Pixel herstelt 20-40% verloren events
- Server-side tracking via eigen domein (t.klantdomein.com)
- Safari ITP omzeild (server-set cookies tot 400 dagen)
- Ad blockers omzeild (GTM via eigen domein)
- BigQuery als centrale databron — alle kanalen in 1 waarheid
- Volledige verkoopcyclus: Lead → MQL (boeking) → SQL (gekwalificeerd) → Klant (waarde)
- ROAS op echte omzet, niet op leads

**Wat je de klant vertelt:**
"Je stuurt niet meer op leads of boekingen. Je stuurt op omzet. Elke euro die je uitgeeft aan ads, kun je terugrekenen naar een klant met een werkelijke waarde."

## De Beexy Pixel (Voxxy Creative Lab proprietary)

Er bestaat geen vergelijkbaar product op de markt. 3 componenten:

### 1. Data Transmitter (browser)
- Draait via client-side GTM in de browser
- Verzamelt data op basis van consent
- Stuurt alles via het eigen domein van de klant naar de server
- Niet via Google, niet via Meta

### 2. Data Receiver (server)
- Draait op de sGTM-container
- Ontvangt data en voedt die in de container
- Vandaar gaan events naar Meta CAPI, GA4, BigQuery, of andere bestemmingen

### 3. GTM Webloader (server)
- Serveert het GTM-script zelf vanaf het first-party domein
- Ad blockers blokkeren googletagmanager.com — maar niet t.klantdomein.com

### Wat het concreet oplost

| Probleem | Zonder Beexy | Met Beexy |
|---|---|---|
| Safari ITP (24u cookie) | fbclid verloren na 24 uur | Server-set cookies tot 400 dagen |
| Ad blockers (~20% NL) | Tracking volledig geblokkeerd | GTM draait via eigen domein |
| Consent compliance | Handmatig per tag | Filtering bij verzameling |
| Zapier-kwetsbaarheid | Multi-stap fragiele keten | Directe server-side datapijplijn |

### Gemeten resultaten

| Metric | Bron |
|---|---|
| 20-40% meer events hersteld | Server-side tracking via first-party domein |
| 30,67% herstel van aankoop-events | Onafhankelijke case study |
| 13% lagere CPA | Meta benchmark bij CAPI naast Pixel |
| 20% hogere lead-to-sale conversieratio | Meta official documentation |
| +35% marketing ROI | BigQuery integratie van 5 platforms |
| +17% advertising ROI | Gecentraliseerde data |
| 20-40% lagere kosten per gekwalificeerde lead | Offline conversie-uploads binnen 45 dagen |
| 2,1x hogere ROAS | CAPI + offline conversiedata (Fever case study) |

## BigQuery als Centraal Datahub

### Waarom

Advertentieplatforms tellen dubbel. Google claimt 500 conversies, Meta claimt 450, terwijl er 600 werkelijke klanten zijn. Zonder centrale data: geen waarheid.

### Wat erin gaat

- Website-events via Beexy Pixel + sGTM
- Meta Ads data (kosten, impressies, klikken)
- CRM-data uit Airtable (leads, boekingen, kwalificaties, deals)
- GA4 (optioneel)
- Perspective Funnels (indien van toepassing)

### Wat eruit komt

Volledige verkoopcyclus meetbaar:

```
Lead (formulier ClickFunnels)
  → MQL: boeking via Calendly
    → SQL: gekwalificeerd na gesprek
      → Klant: waarde bekend
```

Elke stap teruggestuurd naar Meta. Niet als benadering, maar als feitelijk resultaat met werkelijke omzetwaarde.

### High-ticket attributie

High-ticket funnels (€3.000-15.000+ per traject) hebben een attributievenster van minimaal 365 dagen nodig. Standaard Meta (7-28 dagen) mist het merendeel van de conversies in lange verkoopcycli. BigQuery lost dit op.

## Dataverlies-Realiteit (Nederland 2025-2026)

Deze cijfers zijn het argument voor Niveau 3:

| Factor | Impact |
|---|---|
| Ad blockers | ~20% NL, wereldwijd 31,5% |
| Cookie-weigering bij banner | 40,6% van Europese bezoekers |
| Safari ITP (24u cookies) | 25% NL marktaandeel |
| Third-party cookie blokkade | 37% browsers (Safari, Firefox, Brave) |

**Voor high-ticket funnels met beperkte boekingen per maand betekent elk gemist event een reëel verschil in campagneprestaties.**

## Wanneer laden

```
Tracking-gesprek met klant → Niveau 1-2-3 opbouw
Klant vraagt naar ROAS meten → Start bij Niveau 1, verwijs naar 3
Klant heeft al Fase 1 → Verkoop Niveau 2 + 3
sGTM / Beexy / BigQuery vraag → Dit document
meta-ads vraagt naar CAPI/tracking → Verwijs naar tracking-architectuur
Analytics-feedback ziet dataverlies → Verwijs naar Niveau 3
```

## Wanneer NIET laden

- Bij content-productie (ads, pagina's, scripts)
- Bij puur campagne-technische vragen (targeting, budget) → meta-ads
- Bij ad-analyse zonder tracking-component → analytics-feedback
