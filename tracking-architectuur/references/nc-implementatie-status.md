# NC Tracking Implementatie — Live Status

Next Chapter Business tracking-implementatie door Voxxy Creative Lab. Dit document bevat de live configuratie en bekende issues.

**Laatste update:** 13 april 2026

## Technische Identifiers

| Component | Waarde |
|---|---|
| GTM Container | GTM-PRPDBH7V |
| Meta Pixel ID | 1157920582618005 |
| Funneltool | ClickFunnels 2.0 |
| Opt-in domein | weggever.nextchxpter.com |
| Video pagina | weggever.nextchxpter.com/vsl-5-video-b (en varianten A/B) |
| Calendly URL | calendly.com/nextchapterbusiness/kennismaking |
| Post-booking redirect | perspectivefunnel.co (diverse paden) |
| sGTM domein (Fase 3) | t.nextchxpter.com (nog niet actief) |

## Huidige Status per Fase

### Fase 1 — LIVE ✅

| Component | Status |
|---|---|
| GTM geïnstalleerd in CF2.0 Head Code | ✅ Live |
| WinstArchitect cookiebanner | ✅ Live, Consent Mode v2, AP-conform |
| fbclid-capture (first-party cookie) | ✅ Live, werkt vóór consent, stuurt niets naar derden |
| Meta Pixel - PageView (na consent) | ✅ Live |
| Meta Pixel - Lead (formulierinzending + Advanced Matching) | ✅ Live, inclusief PII (e-mail, telefoon, voornaam) |
| Dubbele Pixel verwijderd | ✅ Opgelost (was via CF2.0 native + GTM) |
| CF2.0 native CAPI (Access Token) | ✅ Verwijderd — was server-side buiten consent |

**Klant kan NU campagnes draaien op Lead-optimalisatie.**

### Fase 2 — ICLOSED INTEGRATIE (vervangt Calendly) ⏳

**Strategische shift:** Calendly + Zapier + Airtable keten → iClosed 2-Step Scheduler. Bezit het bookingmoment. Lead capture VÓÓR kalender.

| Component | Status |
|---|---|
| Calendly URL Rewriter (GTM tag) | ✅ Getest — wordt VERWIJDERD bij iClosed migratie |
| iClosed Business account ($120/seat/m) | ⏳ Account aanmaken met NC |
| iClosed event type "Kennismaking" | ⏳ Te configureren |
| 7 kwalificatievragen (ICP Filter) | ⏳ Ontworpen in leadfunnel-v3 doc |
| Type B disqualificatie | ⏳ Vraag 7 = filter, geen kalender |
| Conditional routing (Segment 1/2) | ⏳ Op basis van omzet-vraag |
| iClosed embed in CF2.0 thank you page | ⏳ Vervangt Calendly link |
| Native Meta Pixel in iClosed | ⏳ Pixel ID: 1157920582618005 |
| SMS + email workflows (5 triggers) | ⏳ Bevestiging + 2x herinnering + no-show + non-booker nurture |
| Non-booker email sequence (3 mails) | ⏳ Herkenning → identiteit → confrontatie |
| Bevestigingspagina (CF2.0) | ⏳ Vervangt perspectivefunnel.co 404 |
| Zapier: Calendly → Airtable | ❌ VERVALT — iClosed native CRM sync |
| Zapier: Airtable → Meta CAPI | ⏳ BEHOUDEN voor offline conversies (closed revenue) |

**Wat iClosed oplost:**
- 70% booking drop-off wordt zichtbaar (lead capture vóór kalender)
- Calendly URL Rewriter + Zapier Formatter + utm_content hack = OVERBODIG
- Non-booker retargeting (was onmogelijk met Calendly)
- 404 na boeking (eigen redirect)
- Sales analytics (show rate, close rate, revenue per rep)

**Blocker:** NC moet iClosed Business account aanmaken. Winstarchitect + Voxxy configureren samen.

### Fase 3 — TOEKOMST 🔮

| Component | Status |
|---|---|
| TAGGRS sGTM op t.nextchxpter.com | 🔮 DNS CNAME vereist |
| Beexy Pixel | 🔮 Pixel is af, proces eromheen niet |
| BigQuery centraal datahub | 🔮 Architectuur staat, implementatie na Fase 2 |

## Bekende Issues

### 1. Calendly post-booking redirect → 404

Na een Calendly-boeking wordt de bezoeker doorgestuurd naar perspectivefunnel.co. Die pagina geeft een 404-fout.

**Status:** Wordt opgelost door iClosed migratie — eigen bevestigingspagina in CF2.0 (weggever.nextchxpter.com/bevestiging).

### 2. UTM-encoding complexiteit

NC gebruikt meerdere funnel-varianten (VSL5, A, B, etc.) met eigen UTMs. De fbclid wordt gecodeerd in utm_content samen met de variant.

**Status:** Wordt opgelost door iClosed migratie — iClosed heeft native Meta Pixel integratie. Geen UTM-encoding hack meer nodig.

### 3. GA4 staat nog niet ingesteld

NC maakt momenteel geen gebruik van GA4. Wordt meegenomen in Fase 3.

### 4. Calendly is een gesloten systeem (NIEUW — aanleiding voor iClosed)

Calendly biedt geen eigen tracking, geen doorgave van PII, en beperkte integratiemogelijkheden. De workaround (URL Rewriter + Zapier Formatter + utm_content encoding) is fragiel: als één stap faalt, valt de hele keten weg. Safari (25% NL) beperkt cookies tot 24 uur bij advertentieverkeer. Ad blockers (20% NL) blokkeren fbclid-capture.

**Status:** iClosed vervangt Calendly als booking tool. Native Meta Pixel, lead capture vóór kalender, CRM sync zonder Zapier.

## ClickFunnels Events

| Event | Pagina | PII | Gebruik |
|---|---|---|---|
| cfPageView | Eerste pagina (opt-in) | Nee | PageView trigger |
| cfPageView | Tweede pagina (video) | Ja (na formulier) | Niet nuttig voor tracking |
| cfLead | Tweede pagina (na formulier) | Ja (e-mail, telefoon, naam) | **Lead event voor Meta — cruciale trigger** |

## Open Vragen (status)

### Fase 1 — Beantwoord ✅
- OQ-4: GTM container → GTM-PRPDBH7V ✅
- OQ-6: Access Token → Verwijderd ✅
- OQ-10: Cookiebanner → WinstArchitect banner live ✅

### Fase 2 — iClosed Migratie ⏳
- OQ-1: ~~Calendly abonnement~~ → VERVALT (iClosed vervangt Calendly)
- OQ-2: Airtable kolomstructuur (screenshot nodig — voor offline conversie CAPI)
- OQ-3: ~~Zapier multi-stap~~ → GROTENDEELS VERVALT (alleen nog Airtable → Meta CAPI)
- OQ-5: Meta CAPI access token (Events Manager → Pixel → Settings)
- OQ-9: ~~Calendly embed type~~ → VERVALT (iClosed inline embed)
- OQ-12: (NIEUW) NC akkoord iClosed Business plan ($120/seat/maand)
- OQ-13: (NIEUW) Setter/closer verdeling — wie ontvangt welk segment?
- OQ-14: (NIEUW) NC SMS-nummer voor iClosed workflows (NL mobiel)

### Fase 3 — Open 🔮
- OQ-7: DNS registrar voor nextchxpter.com (CNAME nodig)
- OQ-8: Vimeo embed-code op videopagina (src + query params)
