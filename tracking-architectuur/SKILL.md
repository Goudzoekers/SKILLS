---
name: tracking-architectuur
description: >
  Tracking-, privacy- en attributie-architectuur voor Winstarchitect-partners op ClickFunnels 2.0.
  EXCLUSIEF: GTM-implementatie, Consent Mode v2, cookiebanner, Meta Pixel via GTM, fbclid-capture,
  Calendly-attributie, Zapier→Airtable flows, Meta CAPI (browser + server-side), sGTM via TAGGRS,
  event-deduplicatie, AVG/AP-compliance audits, tracking-diagnose, en fasedocumenten.
  Trigger bij: tracking opzetten, GTM, consent, cookiebanner, pixel, CAPI, fbclid, attributie,
  Calendly tracking, Zapier Airtable koppeling, server-side GTM, TAGGRS, sGTM, deduplicatie,
  AVG compliance, AP handhaving, tracking audit, privacy check, tracking probleem, conversie
  tracking, ClickFunnels tracking, CF2.0 tracking, tracking rapport, tracking diagnose,
  tracking architectuur, tracking voorstel, open vragen klant tracking, ROAS meten.
  NIET triggeren bij: ad copy (goated-ads), campagne setup (meta-ads), pagina's (funnel-pages),
  scripts (funnel-scripts), ad analyse (analytics-feedback), technisch bouwen app (winst-os).
---

# Tracking Architectuur — Privacy-First Attribution Engine

Unicorn-level tracking- en attributie-architectuur voor Winstarchitect-partners. Combineert juridische compliance (AVG/AP) met maximale datakwaliteit voor Meta Ads ROAS-meting.

## Ecosysteem Positie

```
shared-kernel (client brief, ToV)
    ↓
core-story-webinar (Blueprint)
    ↓
funnel-pages + goated-ads + funnel-scripts
    ↓
meta-ads (campagne setup, pixel/CAPI config)
    ↓
► tracking-architectuur ← (GTM, consent, attributie, CAPI, sGTM, compliance)
    ↓
analytics-feedback (data → diagnose → optimalisatie)
```

## Afbakening

| Vraag | Route |
|---|---|
| Tracking opzetten / GTM / consent / pixel | **tracking-architectuur** |
| Tracking audit / compliance check | **tracking-architectuur** |
| fbclid / attributie / Calendly tracking | **tracking-architectuur** |
| sGTM / TAGGRS / CAPI / deduplicatie | **tracking-architectuur** |
| Campagne opzetten / budget / targeting | meta-ads |
| Ad copy / hooks | goated-ads |
| Ad performance analyseren | analytics-feedback |
| Feature bouwen (Supabase, Lovable) | winst-os |

## Context Loading

| Bron | Wanneer |
|---|---|
| `references/3-fasen-architectuur.md` | ALTIJD bij tracking-gerelateerde vraag |
| `references/compliance-checklist.md` | Bij audit, diagnose, nieuw klantproject, AP/AVG vragen |
| `references/open-vragen-template.md` | Bij intake nieuw tracking-project |
| `references/beexy-pixel-voxxy-bigquery.md` | Bij klantgesprek over tracking-waarde, upsell naar Fase 3, ROAS-vragen, dataverlies-discussie, Beexy/sGTM/BigQuery |
| `references/nc-implementatie-status.md` | NC-specifiek: live status, bekende issues, open vragen, technische IDs |
| `shared-kernel/references/revenue-control-system.md` | Bij klantgesprek over tracking: pricing, pitch, offer structuur. De commerciële laag bovenop de techniek. |
| `shared-kernel/references/universal-client-brief.md` | Start nieuw klantproject |

## Voxxy Creative Lab Partnership

Voxxy (Jerry Bierenbroodspot, CTO) is de technische partner voor alle tracking-implementaties. Winstarchitect doet commercie + klantrelatie. Bij tracking-gesprekken gaan we SAMEN het gesprek in.

| Wie | Rol |
|---|---|
| Winstarchitect (Rick) | Klantgesprek, uitleg WAAROM, waardepropositie, upsell Fase 2/3 |
| Voxxy (Jerry) | GTM, consent, scripts, sGTM, CAPI, Beexy Pixel, BigQuery |
| Samen | Architectuurvoorstel, toezegging scope, toekomstpad |

**Verkoopstrategie:** Bouw laag voor laag op. Niveau 1 (Lead-optimalisatie) → Niveau 2 (Boeking-optimalisatie) → Niveau 3 (Volledige attributie met Beexy Pixel + BigQuery). Elk niveau is zelfstandig waardevol. Zie `references/beexy-pixel-voxxy-bigquery.md` voor de volledige 3-niveau pitch.

## De 5 Pijlers

Elke tracking-architectuur rust op 5 niet-onderhandelbare pijlers:

1. **Consent-first** — Geen data naar derden zonder toestemming. Consent Mode v2 default denied. Cookiebanner conform AP-eisen (Nederlands, gelijke knoppen, vóór niet-functionele cookies).
2. **GTM als single orchestrator** — Alle tags, triggers en variabelen via GTM. Geen native pixel-instellingen in CF2.0 of andere funneltools. GTM = SSOT voor alle tracking.
3. **fbclid-persistentie** — fbclid opvangen bij landing, opslaan in first-party cookie (_fbclid, 7d, SameSite=Lax, Secure), doorgeven aan Calendly via UTM-rewriting. Zonder dit: geen attributie.
4. **Deduplicatie via event_id** — Elk event krijgt een UUID. Zelfde ID gaat mee in browser-Pixel én sGTM CAPI. Meta dedupliceert op event_name + event_id (48u venster).
5. **3-fasen uitrol** — Fundament → Attributie → Server-side. Elke fase is zelfstandig waardevol. Geen fase skippen.

## 3-Fasen Architectuur (samenvatting)

Lees `references/3-fasen-architectuur.md` voor volledige specs, scripts en configuraties.

### Fase 1 — Fundament: GTM + Consent + fbclid
- GTM in CF2.0 Head Code
- Consent Mode v2 initialisatie (alle signalen default denied)
- WinstArchitect cookiebanner via GTM (whitelabel Voxxy Creative Lab)
- fbclid Capture tag (GTM Custom HTML, alle pagina's, vóór consent — stuurt niets naar derden)
- Meta Pixel via GTM (alleen na ad_storage: granted)
- Events: PageView, Lead, video milestones, calendly_cta_click, Schedule

### Fase 2 — Attributie: Calendly → Zapier → Airtable → Meta CAPI
- Calendly URL Rewriter (GTM Custom HTML, videopagina) — leest _fbclid cookie, herschrijft Calendly-link
- Zapier workflow: Calendly → Formatter (fbclid extractie) → Airtable
- Zapier workflow: Airtable → Meta CAPI for CRM (action_source: system_generated)
- Meta Offline Conversions API is stopgezet (mei 2025) — gebruik "Facebook Conversions (for Business Admins)"

### Fase 3 — Server-side: sGTM via TAGGRS + Beexy Pixel + BigQuery
- TAGGRS sGTM-container op t.{domein}.com (DNS CNAME vereist)
- transport_url + first_party_collection: true
- **Beexy Pixel** (Voxxy proprietary): Data Transmitter (browser) + Data Receiver (server) + GTM Webloader (server). Lost Safari ITP, ad blockers, en Zapier-kwetsbaarheid op. Zie `references/beexy-pixel-voxxy-bigquery.md`.
- Meta CAPI-tag in sGTM met event_id deduplicatie
- CF2.0 native CAPI definitief vervangen (Access Token verwijderen)
- **BigQuery** als centraal datahub: Lead → MQL → SQL → Klant met werkelijke omzetwaarde. High-ticket attributievenster 365+ dagen.

## Diagnose Protocol

Bij een tracking-audit of -diagnose, doorloop deze 5 checkpunten:

| # | Controle | Ernst als fout |
|---|----------|---------------|
| 1 | Cookiebanner aanwezig + correct (AP-eisen)? | Kritiek — juridisch |
| 2 | Pixel/tags laden alleen na consent? | Kritiek — juridisch |
| 3 | Native CAPI/Access Token in funneltool? | Kritiek — juridisch (buiten consent) |
| 4 | fbclid wordt opgeslagen bij landing? | Hoog — attributie onmogelijk |
| 5 | Calendly/booking-link bevat UTM + fbclid? | Hoog — ROAS niet meetbaar |

Ernst-niveaus: **Kritiek** = actief juridisch risico (AP handhaaft), **Hoog** = attributie/ROAS gebroken, **Middel** = datakwaliteit verminderd.

## Delivery Formaat

Bij een tracking-voorstel of -rapport, lever ALTIJD in deze structuur:

1. **Huidige situatie** — Genummerde problemen met ernstniveau en uitleg
2. **Voorgestelde architectuur** — 3 fasen met scope per fase
3. **Open vragen** — Gegroepeerd per fase, met actie per vraag (zie `references/open-vragen-template.md`)
4. **Meest urgente actie** — Wat de klant VANDAAG moet doen (bijv. Access Token verwijderen)

## Compliance Context (AP april 2025)

De Autoriteit Persoonsgegevens handhaaft actief op cookie-compliance. In april 2025 zijn 50 organisaties formeel gewaarschuwd met een hersteltermijn van 3 maanden. AP-eisen:
- Toestemming vóór niet-functionele cookies
- Gelijke weergave "Alles accepteren" en "Alles weigeren" op eerste laag
- Nederlandse tekst voor Nederlands publiek
- Consent Mode v2 met alle signalen (ad_storage, analytics_storage, ad_user_data, ad_personalization)

## Meest Urgente Actie: Native CAPI Verwijderen

Bij ELKE klant met een funneltool (CF2.0, Systeme, etc.) die een Facebook Access Token in native instellingen heeft: dit is het #1 juridische risico. Deze server-to-server CAPI-koppeling is niet consent-afhankelijk te maken — het is onmogelijk by design. De Access Token moet direct verwijderd worden. Vervangen door consent-gestuurde CAPI via sGTM in Fase 3.

## Quality Gate

**Fase 1:** ☐ Consent Mode v2 default denied ☐ Cookiebanner AP-conform ☐ Pixel alleen na consent ☐ Native CAPI/Access Token verwijderd ☐ fbclid capture actief ☐ Klant screenshots ontvangen

**Fase 2:** ☐ Calendly URL rewriter actief ☐ Zapier flows correct ☐ Airtable kolommen compleet ☐ CAPI boeking-events testen ☐ Open vragen Fase 2 beantwoord

**Fase 3:** ☐ sGTM CNAME actief ☐ Beexy Pixel Data Transmitter live ☐ Beexy Data Receiver ontvangt events ☐ GTM Webloader via eigen domein ☐ CAPI deduplicatie event_id ☐ BigQuery ontvangt data ☐ Volledige verkoopcyclus meetbaar (Lead → MQL → SQL → Klant)
