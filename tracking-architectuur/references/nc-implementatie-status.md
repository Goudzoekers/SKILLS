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

### Fase 2 — KLAARSTAAT, NIET ACTIEF ⏳

| Component | Status |
|---|---|
| Calendly URL Rewriter | ✅ Getest, werkt, nog niet geactiveerd |
| UTM-encoding | utm_content=vsl-5.fbclid_{waarde} |
| Zapier workflow (Calendly → Airtable) | ⏳ Wacht op toegang (Calendly, Zapier, Airtable accounts) |
| Zapier workflow (Airtable → Meta CAPI) | ⏳ Wacht op Zapier + Meta CAPI token |

**Blocker:** Winstarchitect + Voxxy moeten samen met NC om tafel. Voxxy heeft toegang nodig tot Calendly, Zapier en Airtable.

### Fase 3 — TOEKOMST 🔮

| Component | Status |
|---|---|
| TAGGRS sGTM op t.nextchxpter.com | 🔮 DNS CNAME vereist |
| Beexy Pixel | 🔮 Pixel is af, proces eromheen niet |
| BigQuery centraal datahub | 🔮 Architectuur staat, implementatie na Fase 2 |

## Bekende Issues

### 1. Calendly post-booking redirect → 404

Na een Calendly-boeking wordt de bezoeker doorgestuurd naar perspectivefunnel.co. Die pagina geeft een 404-fout. Dit heeft GEEN invloed op tracking maar is slecht voor UX. 

**Fix door NC:** Omleidingspagina aanmaken in CF2.0, óf redirect-URL in Calendly aanpassen naar bestaande pagina.

### 2. UTM-encoding complexiteit

NC gebruikt meerdere funnel-varianten (VSL5, A, B, etc.) met eigen UTMs. De fbclid wordt gecodeerd in utm_content samen met de variant:

```
utm_content=vsl-5.fbclid_test_abc_123
```

Zapier Formatter moet het punt (.) als scheidingsteken gebruiken:
- Links van de punt = funnel-variant
- Rechts van `fbclid_` = de waarde

### 3. GA4 staat nog niet ingesteld

NC maakt momenteel geen gebruik van GA4. Wordt meegenomen in Fase 2/3.

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

### Fase 2 — Open ⏳
- OQ-1: Calendly abonnement (Standard+ vereist voor Zapier)
- OQ-2: Airtable kolomstructuur (screenshot nodig)
- OQ-3: Zapier account + abonnement (Starter+ voor multi-stap)
- OQ-5: Meta CAPI access token (Events Manager → Pixel → Settings)
- OQ-9: Calendly embed type (widget in pagina of redirect)
- OQ-11: Zapier multi-stap beschikbaar?

### Fase 3 — Open 🔮
- OQ-7: DNS registrar voor nextchxpter.com (CNAME nodig)
- OQ-8: Vimeo embed-code op videopagina (src + query params)
