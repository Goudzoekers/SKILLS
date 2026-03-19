# Diagnose Matrix — Ad & Funnel Performance

Systematische diagnose op basis van data-signalen. Gebruik bij elke analyse.

## Ad-Level Diagnose

### Primaire Signalen

| CTR | Hook Rate | CPL | Diagnose | Fix | Skill |
|---|---|---|---|---|---|
| ❌ Laag | ❌ Laag | ❌ Hoog | Hook faalt — mensen scrollen door | Nieuwe hooks schrijven | goated-ads |
| ❌ Laag | ✅ Hoog | ❌ Hoog | Hook pakt maar body/CTA overtuigt niet | Body en CTA herschrijven | goated-ads |
| ✅ Hoog | ✅ Hoog | ❌ Hoog | Ad werkt maar landing page faalt | Pagina optimaliseren | funnel-pages |
| ✅ Hoog | ✅ Hoog | ✅ Laag | WINNER | Schalen + kaleidoscoop | analytics-feedback |
| ✅ Hoog | ❌ Laag | ✅ Laag | Thumbnail/visual trekt maar hook verliest | Hook verbeteren, visual behouden | goated-ads |
| ❌ Laag | — | ✅ Laag | Kleine maar kwalitatieve audience | Voorzichtig schalen, niet veranderen | — |

### Secundaire Signalen

| Signaal | Betekenis | Actie |
|---|---|---|
| Frequency > 3 | Audience uitgeput | Breder targeten of nieuwe creative |
| Frequency > 5 | Creative dood | Nieuwe ads maken, pauzeer huidige |
| Ad > 4 weken actief | Vermoeidheid waarschijnlijk | Kaleidoscoop variaties maken |
| CPM stijgt snel | Concurrentie of relevance score daalt | Check relevance, evt. audience shift |
| CTR daalt over tijd | Creative wear-out | Nieuwe hooks, zelfde meat mag |
| Hoge CTR maar 0 conversies | Verkeerde klik-incentive of pagina-mismatch | Check congruence ad↔pagina |

## Funnel-Level Diagnose

### Stap-voor-Stap Waterval

```
Ad Impressies → [CTR] → Klikken → [CR] → Registraties → [Show%] → Shows → [Close%] → Sales
```

Analyseer van LINKS naar RECHTS. Fix de eerste bottleneck eerst.

| Stap | Metric | Benchmark | Als onder benchmark |
|---|---|---|---|
| Ad → Klik | CTR | >1.5% | Hooks/creative probleem → goated-ads |
| Klik → Registratie | Opt-in CR | >25% | Pagina-probleem → funnel-pages |
| Registratie → Show | Show rate | >30% | Nurture-probleem → pre-mails + reminders |
| Show → Einde webinar | Retentie | >40% | Content-probleem → core-story-webinar |
| Einde → Klik aanbod | Pitch klik | >10% | Pitch-probleem → core-story-webinar |
| Klik → Aankoop | Close rate | >5% | Sales page / post-mails → funnel-pages |

### Congruence Check

Als CTR hoog is maar opt-in CR laag:
```
DIAGNOSE: Disconnect tussen ad en landing page
CHECK:
1. Komt de headline van de pagina overeen met de ad-belofte?
2. Ziet de pagina er betrouwbaar uit (design, snelheid)?
3. Is het formulier te lang?
4. Laadt de pagina snel genoeg (<3 sec)?
```

## Classificatie-Systeem

Na analyse, classificeer elke ad:

| Categorie | Criteria | Actie |
|---|---|---|
| 🏆 Winner | Top 20% op CPL + volume | Budget verhogen (max +20-30% per 3 dagen) |
| 📊 Potential | 1 metric goed, 1 slecht | Fix het zwakke element, hertest |
| ❌ Kill | Bottom 20% na 1000+ impressies | Uitzetten, niet repareren |
| 🧪 Onvoldoende data | <1000 impressies | Meer budget/tijd geven |

## Rapport Template

```
## Samenvatting
- Periode: [datum - datum]
- Totaal spend: €[X]
- Totaal leads: [X]
- Gemiddelde CPL: €[X]
- Beste ad: [naam/ID]
- Slechtste ad: [naam/ID]

## Winners (schalen)
[Per winner: naam, metrics, waarom het werkt, schaal-advies]

## Potentials (fixen)
[Per potential: naam, metrics, wat er mis is, concrete fix]

## Kill (uitzetten)
[Per kill: naam, metrics, waarom stoppen]

## Actieplan
1. [Actie 1 — welke skill — deadline]
2. [Actie 2]
3. [Actie 3]

## Kaleidoscoop Suggesties
[Variaties op winners — welke techniek, verwachte impact]
```
