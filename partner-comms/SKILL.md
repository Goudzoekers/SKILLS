---
name: partner-comms
description: >
  Genereer professionele klantcommunicatie voor Winstarchitect-partners. EXCLUSIEF voor
  operationele berichten: Slack onboarding, Weekly Pulse, milestone updates, performance
  samenvattingen, escalatie-protocol, meeting agendas. Trigger bij: onboarding bericht,
  welkomstbericht, Slack bericht schrijven, weekly pulse, weekupdate, klant update, milestone,
  klantcommunicatie, partner bericht, status update, check-in, recap, escalatie, meeting agenda,
  kickoff. NIET triggeren bij: advertentieteksten (goated-ads), pagina copy (funnel-pages),
  video scripts (funnel-scripts), webinar content (core-story-webinar), technisch bouwen (winst-os).
---

# Partner Comms — Communicatie Engine

Operationele communicatielaag voor Winstarchitect-klanten. Loopt parallel aan het content-
productieproces uit het Orchestratie Protocol.

## Positie in het Ecosysteem

```
Orchestratie Protocol          Partner Comms (deze skill)
─────────────────────          ──────────────────────────
Stap 0: Client Brief     →    Slack Onboarding Bericht
Stap 1: ToV Kalibratie   →    (geen apart bericht — onderdeel van Brief)
Stap 2: Blueprint         →    Milestone Update: "Blueprint klaar"
Stap 3: Pages/Ads/Scripts →    Milestone Update: "Funnel klaar voor review"
Stap 4: Quality Gate      →    Milestone Update: "Live-ready"
Stap 5: Launch + Iteratie →    Weekly Pulse (doorlopend)
```

Partner Comms produceert GEEN content. Het informeert de klant over het proces.

## Context Loading

> **Wet 6: Laad het minimum, niet het maximum.** Partner-comms is operationeel — geen content-frameworks nodig. Alleen templates + schrijfregels + ToV.

| Nodig | Bron | Wanneer |
|---|---|---|
| Templates per berichttype | `references/templates.md` | ALTIJD |
| Schrijfregels NL | `shared-kernel/references/schrijfregels-nl.md` | Bij elk bericht |
| ToV-profiel klant | Client Brief (als beschikbaar) | Personalisatie |

**Check eerst:** Is er een Client Brief? Gebruik de klantnaam en relevante context.
Geen brief? Vraag minimaal: naam, niche, startdatum, dashboardlink.

## De Vijf Berichttypen

### 1. Slack Onboarding
**Wanneer:** Direct na ondertekening/betaling.
**Doel:** Verwachtingen zetten, werkwijze uitleggen, eerste actie triggeren.
**Structuur:** Zie `references/templates.md` → Onboarding.

### 2. Weekly Pulse
**Wanneer:** Elke maandag.
**Doel:** Klant op de hoogte houden zonder dat ze hoeven vragen.
**Structuur:** Focus + Inzichten + Acties + Input nodig.
**Datafeed:** Als er campagnedata is → gebruik analytics-feedback output als input.

### 3. Milestone Update
**Wanneer:** Bij afronding van een fase uit het Orchestratie Protocol.
**Doel:** Klant informeren dat een deliverable klaar is + wat de volgende stap is.
**Varianten:** Blueprint klaar, Funnel review-ready, Live-ready, Eerste resultaten.

### 4. Performance Samenvatting
**Wanneer:** Maandelijks of bij significante data.
**Doel:** Resultaten duiden in klant-taal (geen jargon).
**Datafeed:** analytics-feedback output als input. Vertaal CPL/CTR/ROAS naar "wat betekent dit voor jou."

### 5. Escalatie / Urgentie
**Wanneer:** Iets vereist onmiddellijke actie van de klant.
**Doel:** Kort, helder, één actie.
**Regel:** Nooit meer dan één vraag per escalatiebericht.

## Harde Regels

- **Toon:** Professioneel, warm, kort. Geen overmatige emoji. Geen uitroeptekens-inflatie.
- **Lengte:** Elk bericht past op één telefoonscherm. Scrollen = te lang.
- **Structuur:** Duidelijke secties met witruimte. Geen muren van tekst.
- **Perspectief:** "Ik" (niet "wij" tenzij er een team achter zit).
- **Actie:** Elk bericht eindigt met wat er nu gebeurt of wat de klant moet doen.
- **Geen verbindingstekens.** Geen "gratis webinar" als combinatie.
- **Personaliseer:** Gebruik de klantnaam. Refereer aan hun niche/aanbod waar relevant.
- **Afsluiting:** "— Rick" (of de naam uit de brief). Geen "Met vriendelijke groet."

## Output

Plaintext (voor Slack) of .docx als de klant dat prefereert.
Bestandsnaam bij .docx: `[klantnaam]-[berichttype]-partner-comms.docx`

## Quality Check

Voor verzending, controleer:
- [ ] Past op één telefoonscherm?
- [ ] Is er precies één duidelijke actie of conclusie?
- [ ] Staat de klantnaam erin?
- [ ] Geen jargon dat de klant niet begrijpt?
- [ ] Geen verbindingstekens?
- [ ] Eindigt met een concrete volgende stap?
