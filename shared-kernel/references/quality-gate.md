# Quality Gate — 3-Laags QA Systeem

Doorlopen NA elke module, VOOR presentatie aan klant/partner. Output die niet door alle 3 lagen komt: herschrijf proactief.

## Laag 1: Blindtest (Is het herkenbaar?)

Stel je voor dat de doelgroep dit leest ZONDER context. Zonder te weten van wie het komt of wat het product is.

| Check | Vraag | Fail = |
|---|---|---|
| Herkenning | Denkt de lezer binnen 3 seconden "dit gaat over mij"? | Te vaag of te breed |
| Specificiteit | Staan er concrete details in (namen, cijfers, scenario's)? | Generieke copy |
| Emotie | Voelt de lezer iets (herkenning, pijn, hoop, urgentie)? | Rationele opsomming |
| Actie | Is het glashelder wat de volgende stap is? | Vage of ontbrekende CTA |

**Regel:** Als je "dit kan over elke niche gaan" kunt zeggen → FAIL.

## Laag 2: Technische Check (Klopt het ambacht?)

| Check | Criterium |
|---|---|
| Schrijfregels NL | Max 3 zinnen/alinea, max 8 woorden/bullet, actieve vorm |
| Zonder/zodat | Elk voordeel bevat emotionele context |
| Verboden woorden | Geen items van de blacklist (zie schrijfregels-nl.md) |
| AI-detectie | Geen zinnen die "AI-geschreven" verraden (zie tov-kalibratie.md) |
| **ToV Scorecard** | **Per-parameter check — zie hieronder** |
| Anti-taal check | Nul hits op klant-specifieke anti-taal lijst (zoek-en-vervang) |
| Signature patronen | Minimaal 2 signature patronen zichtbaar in de output |
| Alter Ego match | Bij multi-person merk: past de toon bij de juiste persoon? |
| Mobile-first | Ziet het er goed uit op een telefoonscherm? |
| CTA-herhaling | Minimaal 3x per pagina/mail |
| Headline-kracht | Headline werkt zelfstandig zonder body |
| Eerste 5 woorden | Bevatten triggerwoord of call-out |
| Ritme | Variatie in zinslengte (kort-lang-kort) |

### ToV Scorecard (vervangt de oude binary "ToV-match" check)

Score elke parameter op match met het gekalibreerde profiel. Schaal: ✅ (match), ⚠️ (±2 afwijking), ❌ (>2 afwijking).

| # | Parameter | Profiel-score | Output-score | Match |
|---|---|---|---|---|
| 1 | Formaliteit | [uit profiel] | [schat in] | ✅/⚠️/❌ |
| 2 | Directheid | | | |
| 3 | Humor | | | |
| 4 | Autoriteit | | | |
| 5 | Emotie | | | |
| 6 | Tempo | | | |
| 7 | Inclusiviteit | | | |
| 8 | Kwetsbaarheid | | | |
| 9 | Jargon | | | |
| 10 | Provocatie | | | |

**Pass:** Max 2x ⚠️, 0x ❌.
**Focus:** Check de top-3 extreme parameters EERST — dat zijn de parameters die het merk het meest herkenbaar maken. Als die 3 matchen, klopt de rest meestal ook.

**Voorbeeld (NC profiel: directheid 9, provocatie 8, formaliteit 2):**
- Ad bevat "Misschien wil je eens kijken naar..." → Directheid = 3/10 → ❌ FAIL
- Ad bevat "Stop met jezelf voor de gek houden." → Directheid = 9/10 → ✅ PASS

## Laag 3: Strategische Check (Werkt het in de funnel?)

| Check | Vraag |
|---|---|
| Funnel-consistentie | Sluit deze output aan op wat ervoor EN erna komt? |
| Awareness-match | Past het awareness-niveau bij de positie in de funnel? |
| Belofte-congruence | Komt de belofte uit de ad overeen met de pagina? |
| Bezwaar-dekking | Zijn de top-3 bezwaren van deze niche geadresseerd? |
| Bewijs-integratie | Is er bewijs/proof meegenomen (niet alleen claims)? |
| P.I.G.-check | Is de Primal Drijfveer aanwezig (niet alleen oppervlakte-wens)? |
| Escalatie-logica | Bouwt elk element voort op het vorige? |

## Scoring

| Score | Betekenis | Actie |
|---|---|---|
| 3/3 lagen pass | Klaar voor presentatie | Opleveren |
| 2/3 lagen pass | Bijna | Fix de failing laag, doorloop opnieuw |
| 1/3 of 0/3 | Niet klaar | Herschrijf, niet repareer |

## Snelle Self-Check (7 vragen)

Voor als je haast hebt — deze 7 vangen 90% van de fouten:

1. Zou IK hierop klikken als ik de doelgroep was?
2. Kan ik "dit is generiek" zeggen? → herschrijf
3. Staat er een concreet getal of naam in?
4. Weet de lezer EXACT wat de volgende stap is?
5. Klinkt het als de klant/partner of als een AI?
6. Herken ik minimaal 2 signature patronen van dit merk?
7. Bevat het nul woorden van de anti-taal lijst?
