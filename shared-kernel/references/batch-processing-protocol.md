# Batch Processing Protocol — Meerdere Klanten Parallel

Laden bij >5 actieve klanten. Voorkomt chaos, vergissingen en ToV-vervuiling tussen klanten.

## Lifecycle Fasen per Klant

| Fase | Status | Prioriteit | Actie |
|---|---|---|---|
| 0 | Intake | Hoog | Brief + ToV kalibratie |
| 1 | Blueprint | Hoog | Perceptie Blueprint bouwen |
| 2 | Build | Medium | Pages + Ads + Scripts + Webinar |
| 3 | Launch | Hoog | Quality Gate + live zetten |
| 4 | Optimize | Doorlopend | Data → diagnose → fix |
| 5 | Scale | Doorlopend | Kaleidoscoop + expansie |

## Prioritering

**Urgentie-matrix:**
```
        HOOG IMPACT
            |
  Fase 3    |    Fase 0-1
  (Launch)  |    (Intake/Blueprint)
            |
URGENT -----+------ NIET URGENT
            |
  Fase 4    |    Fase 2
  (Optimize)|    (Build)
            |
        LAAG IMPACT
```

**Vuistregel:** Klanten in Fase 0-1 en Fase 3 altijd eerst. Fase 2 kan parallel. Fase 4-5 in vaste cycli.

## ToV-Isolatie

**KRITIEK:** Bij het wisselen tussen klanten, herlaad ALTIJD het ToV-profiel. Nooit copy schrijven voor Klant B terwijl je ToV van Klant A nog in je hoofd hebt.

**Protocol:**
1. Open het ToV-profiel van de klant
2. Lees de 3 testfragmenten
3. Schrijf 1 testzin in hun stem
4. Pas dan pas de module aan

## Weekplanning Template

| Dag | Focus |
|---|---|
| Maandag | Nieuwe intakes + Blueprint werk (Fase 0-1) |
| Dinsdag-Woensdag | Build werk (Fase 2) — ads, pages, scripts |
| Donderdag | Quality Gate reviews + launches (Fase 3) |
| Vrijdag | Analyse + iteratie (Fase 4-5) |

## Parallelle Build-Regels

- Max 3 klanten tegelijk in Fase 2 (Build)
- Elke klant heeft een eigen werkmap/document
- Nooit copy voor 2 klanten in dezelfde sessie zonder ToV-reset
- Bij twijfel over ToV: pauzeer en herlaad het profiel

## Escalatie

| Signaal | Actie |
|---|---|
| >10 klanten in Fase 2 | Extra capaciteit of fasering |
| Klant >2 weken in zelfde fase | Blocker identificeren, escaleren |
| Metrics dalen bij meerdere klanten | Systeem-issue, niet klant-issue → shared-kernel reviewen |
| ToV-vervuiling gedetecteerd | Stop, herlaad, herschrijf betreffende output |
