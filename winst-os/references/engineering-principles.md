# Engineering Principles — Universeel Technisch Framework

Project-agnostische principes voor alle technische bouwprojecten. Gedistilleerd uit Winst OS en portfoliobedrijven.

## De 4 Wetten

### Wet 1: Het systeem beslist nooit — het informeert
Het platform presenteert data, opties en gevolgen. De gebruiker (architect/eigenaar) neemt de beslissing. Geen automatische acties die de business beïnvloeden zonder expliciete goedkeuring.

### Wet 2: Stabiliteit > Features
Nieuwe features mogen nooit bestaande functionaliteit breken. Bij twijfel: niet shippen. Een werkend systeem met 5 features verslaat een buggy systeem met 50 features.

### Wet 3: SSOT — Single Source of Truth
Elk stuk data leeft op precies één plek. Geen duplicatie. Als je dezelfde informatie op twee plekken moet updaten, is de architectuur fout.

### Wet 4: Fix de bron, niet de output
Als je dezelfde output-correctie meer dan 2x maakt, is het probleem niet de output maar de bron. Ga upstream en fix het daar.

## Pre-Flight Protocol

Doorloop VOOR je begint te bouwen:

```
1. WAT is het probleem? (1 zin)
2. VOOR WIE is dit? (specifieke gebruiker/rol)
3. WAT is de gewenste uitkomst? (meetbaar)
4. WAT zijn de constraints? (tech stack, budget, tijd)
5. WAT kan er misgaan? (top 3 risico's)
6. HOE meten we succes? (KPI)
```

## Stage Contract Pattern

Elk bouwstadium volgt dit format:

```
INPUTS:    [Wat heb ik nodig om te beginnen?]
PROCESS:   [Wat doe ik precies?]
OUTPUTS:   [Wat lever ik op?]
VERIFY:    [Hoe weet ik dat het klopt?]
```

**Regel:** Geen stage begint zonder dat de INPUTS compleet zijn. Geen stage is af zonder VERIFY.

## Context Engineering

### Factory vs. Product
- **Factory** = de configuratie, schemas, templates, rules die de output bepalen (stabiel, verandert zelden)
- **Product** = de werkelijke output die per run/klant/situatie anders is (variabel)

**Regel:** Als je herhaaldelijk de Product-output corrigeert, is de Factory fout. Fix de Factory.

### Edit-Source Principe
```
Output fout? → Trace terug naar de bron → Fix de bron → Regenereer output
NOOIT: Output fout → Fix de output direct → Hoop dat het niet weer gebeurt
```

### Cross-Stage Traceability
Elke output moet traceerbaar zijn naar zijn bron. De 60-seconden regel: binnen 60 seconden moet je kunnen achterhalen WAAROM een bepaalde output zo is.

### U-Shaped Intervention
```
Niveau 1 (oppervlak): Output-fix → tijdelijk, herhaalt zich
Niveau 2 (midden): Process-fix → beter, maar symptoombestrijding
Niveau 3 (diep): Source-fix → permanent, voorkomt herhaling

Altijd streven naar Niveau 3.
```

## Architectuur-Principes

### Database = SSOT
De database is de enige bron van waarheid. De UI leest en schrijft naar de database. Nooit lokale state als bron van waarheid.

### Naming Conventions
- Consistente naamgeving door het hele systeem
- Database tabelnamen = meervoud Engels (bijv. `partnerships`, niet `partner`)
- Functies = beschrijvend (bijv. `calculateMonthlyRevenue`, niet `calc`)
- Geen afkortingen tenzij universeel begrepen (ID, URL, API)

### Error Handling
- Elke externe call kan falen → altijd error handling
- Gebruiker ziet NOOIT een technische fout → altijd een menselijke boodschap
- Log ALLES server-side → debug later
- Observability logging (`logOpsRun()`) nooit awaiten — fire and forget

### Security Defaults
- Row Level Security (RLS) op elke tabel
- Geen data zonder authenticatie
- Principle of least privilege: gebruikers zien alleen hun eigen data
- API keys nooit in frontend code

## Code Quality Checklist

- ☐ Werkt het? (functioneel correct)
- ☐ Breekt het iets anders? (regressie check)
- ☐ Is het leesbaar? (kan iemand anders het begrijpen)
- ☐ Is het DRY? (geen onnodige duplicatie)
- ☐ Is het testbaar? (kun je verifiëren dat het werkt)
- ☐ Is het veilig? (auth, RLS, input validation)
- ☐ Is het performant? (geen onnodige queries, geen N+1)
- ☐ Volgt het de 4 Wetten?

## Deployment Protocol

```
1. Ontwikkel lokaal / in branch
2. Test alle happy paths + edge cases
3. Review (zelf of peer)
4. Merge naar staging
5. Smoke test op staging
6. Deploy naar productie
7. Monitor eerste 24 uur
8. Pas aan indien nodig
```

**Regel:** Nooit direct naar productie deployen zonder staging-test. Nooit op vrijdagmiddag deployen.

## Communicatie met de Architect

De architect (Winstarchitect / eigenaar) is NOOIT operationeel. Maximaal 5 calls per week. Communicatie via:
1. Async berichten voor updates
2. Calls alleen voor beslissingen
3. Dashboard voor metrics
4. Alerts alleen voor kritieke issues
