# Compliance Checklist — AVG / AP Tracking Audit

Gebruik dit bij elke tracking-audit of diagnose. Doorloop elk punt en noteer Ernst + Status.

## Ernst-niveaus

| Ernst | Betekenis | Actie |
|-------|-----------|-------|
| Kritiek | Actief juridisch risico, AP handhaaft | Direct oplossen, blokkeert alles |
| Hoog | Attributie/ROAS gebroken | Oplossen in Fase 1-2 |
| Middel | Datakwaliteit verminderd | Oplossen in Fase 2-3 |

## Audit Checklist

### Juridisch (Kritiek)

- [ ] **Cookiebanner aanwezig?** — Zonder banner = directe AVG-overtreding. AP heeft in april 2025 50 organisaties gewaarschuwd, hersteltermijn 3 maanden.
- [ ] **Cookiebanner AP-conform?** — Nederlandse tekst, gelijke weergave "Alles accepteren" en "Alles weigeren" op eerste laag, toestemming vóór niet-functionele cookies.
- [ ] **Pixel laadt alleen na consent?** — Check browser DevTools → Network → filter op "facebook". Als fbevents.js laadt zonder consent: kritiek.
- [ ] **Native CAPI/Access Token in funneltool?** — CF2.0 → Site Settings → Tracking Code → Facebook. Als Access Token aanwezig: server-side CAPI buiten consent. Meest urgent probleem.
- [ ] **Geen andere tracking-scripts buiten GTM?** — Check Head Code, Body Code, Footer Code voor hardcoded pixels of scripts die buiten GTM om laden.

### Attributie (Hoog)

- [ ] **fbclid wordt opgeslagen?** — Check browser cookies voor `_fbclid` na landing met `?fbclid=test`. Als niet aanwezig: attributie onmogelijk.
- [ ] **Calendly-link bevat UTM-parameters?** — Inspecteer de href van de Calendly-link na pageload. Moet bevatten: utm_content=fbclid_XXX, utm_source=meta.
- [ ] **Zapier flow actief?** — Calendly → Formatter → Airtable met fbclid-extractie.
- [ ] **Airtable kolom fbclid aanwezig en gevuld?** — Check recente records.

### Datakwaliteit (Middel)

- [ ] **Consent Mode v2 correct geconfigureerd?** — Check GTM → Tags → Consent Initialization. Alle 4 signalen default denied.
- [ ] **Event deduplicatie actief?** — Check of event_id (UUID) meegaat in browser-Pixel én sGTM CAPI.
- [ ] **sGTM CNAME actief?** — DNS check: `dig t.{domein}.com CNAME`. Moet resolven naar TAGGRS endpoint.
- [ ] **fbc-formaat correct in CAPI payload?** — Format: `fb.1.{ms_timestamp}.{fbclid}`

## Veelvoorkomende Problemen per Funneltool

### ClickFunnels 2.0
- Native Facebook Pixel toggle in Site Settings → Tracking Code — moet UIT
- Native Access Token in zelfde sectie — moet LEEG
- URL-parameters verdwijnen bij paginaovergang — fbclid capture vereist
- Geen native consent-oplossing — extern via GTM + cookiebanner

### Systeme.io
- Vergelijkbare native pixel-integratie — zelfde risico's
- Beperkter Head Code-ondersteuning

### WordPress + Elementor
- Meer flexibiliteit via GTM
- Let op: sommige plugins laden eigen tracking buiten GTM om

## AP Handhavingscontext (april 2025)

De Autoriteit Persoonsgegevens heeft in april 2025:
- 50 organisaties formeel gewaarschuwd voor cookie-overtredingen
- Hersteltermijn van 3 maanden gesteld voordat boetes volgen
- Specifiek geëist: toestemming vóór niet-functionele cookies, gelijke knoppen, Nederlandse tekst

Dit maakt tracking-compliance geen "nice to have" maar een juridische verplichting met actieve handhaving.
