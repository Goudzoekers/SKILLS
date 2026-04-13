# Revenue Control System™ — Winstarchitect Offer Architectuur

Dit is hoe Winstarchitect zichzelf positioneert en verkoopt. Niet als agency. Als architect van omzetdata.

**Kernpositionering:** Je wordt niet betaald voor werk. Je wordt betaald voor impact. Het verschil tussen een agency en een architect is: de agency levert uren, de architect bepaalt welke data je vertrouwt en waar je geld naartoe gaat.

## De Pitch (dit is wat je zegt)

> Op dit moment mis je een significant deel van je omzet in je data. 20-40% is onzichtbaar of verkeerd toegewezen. Daardoor stuur je je budget verkeerd aan.
>
> Wij herstellen die datastroom en koppelen echte omzet terug naar je campagnes. Vanaf dat moment groeit je account niet door gokken, maar door meten.

**Niet uitleggen wat je bouwt.** Niet praten over GTM, sGTM, CAPI, BigQuery. Dat is het HOE. De klant koopt het WAAROM: ze missen geld en weten het niet.

## Aanbod — 3 Lagen

### 1. INSTALL (eenmalig)

**Doel:** Datalekken dichten + waarheid bouwen.

**Wat je levert:**
- Dubbele / corrupte tracking fixen
- Consent + AVG compliant maken (cookiebanner, Consent Mode v2)
- Server-side tracking (Meta CAPI via sGTM)
- First-party data layer (fbclid / identifiers, Beexy Pixel)
- Koppeling funnel → booking → CRM:
  - ClickFunnels / Perspective → Calendly → Airtable
  - Of custom stack als klant groeit
- Event mapping van de volledige verkoopcyclus:
  - Lead → Booking → Close → Revenue
- Eerste revenue feedback loop naar Meta

**Prijs:**
- **Target: €6.000 — €10.000**
- Huidige prijs: €2.500 (ondermijnt jezelf — dit is maanden werk + proprietary tech)
- €2.500 is een startpunt voor eerste klanten, niet het eindpunt

**Migratie-pad van huidig naar target:**
1. Huidige klanten: eerlijk gesprek. "De scope is groter dan wat we initieel bespraken. Dit is wat het werkelijk omvat."
2. Nieuwe klanten: start op €4.000-6.000. Bouw naar €10.000 met case studies als bewijs.
3. Premium klanten (€500K+ omzet): €10.000+ is gerechtvaardigd door de omzetimpact.

### 2. CONTROL (maandelijks)

**Doel:** Waarheid bewaken + systeem laten draaien.

**Wat je beheert:**
- Server-side GTM + CAPI
- Data pipelines (Zapier eruit faseren waar mogelijk)
- BigQuery / data opslag
- Event debugging / monitoring
- Consent checks (AP-compliance doorlopend)
- Weekly data audits
- Attribution checks

**Wat de klant krijgt:**
- Stabiele datastromen
- Minder verlies door browsers / adblockers
- Betrouwbare cijfers waar ze op kunnen sturen

**Prijs:**
- **Target: €1.500 — €3.000 / maand**
- Huidige situatie: retainer moet nog besproken worden
- Geen discussie. Dit is infrastructuur. Geen infrastructuur = geen data = blind sturen.

**Positionering:** "Je betaalt niet voor onderhoud. Je betaalt voor de garantie dat je data klopt. Zonder dit stuur je op leugens."

### 3. GROWTH (performance fee)

**Hier zit het echte geld.**

Drie varianten, van minimaal acceptabel tot optimaal:

**Variant A — Minimaal acceptabel:**
- 3-5% op Meta attributed revenue
- Eenvoudig te meten, laagdrempelig voor de klant
- Huidige situatie: 3% uit dealwaarde via Meta als bron

**Variant B — Correct:**
- 5-10% op closed revenue uit jouw tracking
- Alles wat via jouw systeem als klant binnenkomt
- Vereist: toegang tot CRM + sales data

**Variant C — Beste model (uplift):**
- Baseline → uplift model
- Huidige omzet = baseline (vastleggen bij start)
- Alles daarboven = jouw impact
- **10-15% van uplift**
- Vereist: baseline-meting bij start + maandelijkse rapportage

**Kritieke voorwaarde voor alle varianten:**
- Baseline vastleggen bij start (huidige omzet, CPL, CPA, close rate)
- Toegang tot CRM eisen (Airtable, sales data)
- Maandelijkse rapportage van werkelijke omzet
- Zonder baseline: geen bewijs van impact = geen performance fee

**Migratie van 3% naar 5-10%:**
1. Huidige klanten: lever eerst de data-waarheid (INSTALL + CONTROL). Laat ze zien wat ze misten.
2. Zodra BigQuery draait: "We kunnen nu precies laten zien welke omzet via ons systeem binnenkwam. Hier zijn de cijfers."
3. Dan het gesprek: "Op basis van deze data is [Variant B of C] eerlijker voor ons beiden."

## Huidige Pricing vs Target

| Component | Nu | Target | Gap |
|---|---|---|---|
| Tracking (eenmalig) | €2.500 | €6.000-10.000 | Onderwaardeert proprietary tech + maanden werk |
| Meta Ads retainer | €750/m | €1.500-2.000/m (ads) + €1.500-3.000/m (CONTROL) | Split in twee: ads management + data infrastructure |
| Performance fee | 3% dealwaarde | 5-10% closed revenue of 10-15% uplift | Vereist data-bewijs + baseline |

**De shift:** Van "ik manage je ads" naar "ik bepaal welke data je vertrouwt en waar je geld naartoe gaat." De ads management is een ONDERDEEL van het Revenue Control System. Niet het hoofdproduct.

## Tracking Architectuur (wat je verkoopt zonder het zo te noemen)

De klant hoort: "we herstellen je omzetdata." Wat je bouwt:

### 1. Capture
- First-party cookies (server-set via Beexy Pixel)
- fbclid persistence (7 dagen → 400 dagen met server-set)
- Consent-based firing (Consent Mode v2)
- Enriched events (Advanced Matching: e-mail, telefoon, naam)

### 2. Transport
- Server-side GTM via TAGGRS
- Eigen subdomein (t.klantdomein.com)
- Events naar Meta CAPI / GA4

### 3. Storage
- BigQuery = enige waarheid
- Combineert: ads data + site events + CRM data
- Attributievenster: 365+ dagen (vs Meta standaard 7-28 dagen)

### 4. Attribution
- Lead → Booking → Close → Revenue
- Lange window voor high-ticket (essentieel)
- Cross-channel deduplicatie (Google + Meta tellen niet meer dubbel)

### 5. Feedback Loop
- Omzet terug naar Meta via CAPI
- Betere optimalisatie → lagere CPA → hogere ROAS
- **Dit is de cirkel die geld genereert.** Zonder feedback loop: je optimaliseert op leads. Met feedback loop: je optimaliseert op omzet.

## Positionering: Waarom Dit Werkt

- **Je zit op de money layer, niet de marketing layer.** Iedereen kan ads schrijven. Niemand bezit de omzetdata.
- **Je claimt wat anderen niet zien.** 20-40% van de conversies is onzichtbaar voor standaard tracking. Jij maakt het zichtbaar.
- **Je wordt betaald op uitkomst, niet op uren.** De performance fee is direct gekoppeld aan omzet die JIJ zichtbaar maakte.
- **Je bent moeilijk te vervangen.** De Beexy Pixel is proprietary. BigQuery + sGTM + CAPI is een architectuur die maanden kost om op te zetten. Migreren = alles opnieuw.

## Wat Dit Laat Mislukken

1. **Geen baseline vastleggen** — Zonder startpunt kun je geen uplift bewijzen. Altijd een 0-meting doen bij INSTALL.
2. **Geen toegang tot CRM eisen** — Als je de sales data niet hebt, kun je closed revenue niet meten. CRM-toegang is non-negotiable.
3. **Blijven hangen in tools** — De klant hoort niet over GTM, Zapier, BigQuery. Ze horen over omzet, data, en beslissingen.
4. **Jezelf positioneren als uitvoerder** — "Ik fix tracking" = uitvoerder. "Ik bepaal welke data je vertrouwt" = architect. Nooit het eerste.
5. **Prijs te laag houden** — €2.500 eenmalig + €750/m ondermijnt de waardepropositie. Als je de data-laag bezit die hun hele business aanstuurt, is €6-10K + €1.5-3K/m + performance fee het minimum.

## Perfect Offer Structuur (voor de pitch)

### Stap 1: Audit (gratis, 30 min)

"Ik kijk naar je huidige tracking en laat je in 30 minuten zien hoeveel je mist."

- Diagnose Protocol doorlopen (5 checkpunten)
- Laat de 5 actieve problemen zien (consent, dubbele pixel, CAPI buiten consent, geen attributie, etc.)
- Eindig met: "Dit is wat je nu mist. Wil je weten wat dat kost?"

### Stap 2: Voorstel (Revenue Control System pitch)

"Op basis van de audit: je mist [X]% van je conversiedata. Bij jouw omzet is dat €[Y] per maand aan onzichtbare impact."

- Concrete berekening: hun omzet × 20-40% = wat ze missen
- Het 3-lagen aanbod presenteren: INSTALL → CONTROL → GROWTH
- Baseline vastleggen als startpunt

### Stap 3: Commitment

"We starten met INSTALL. Ik heb toegang nodig tot: GTM, Meta Business Manager, CRM, Calendly. En we leggen vandaag je baseline vast."

- Toegang eisen = autoriteit claimen
- Baseline = het fundament voor de performance fee later
- Verwachting managen: "Fase 1 draait binnen 2 weken. De volle architectuur binnen 6-8 weken."

### Stap 4: Upsell naar GROWTH (na 30-60 dagen)

"Je ziet nu wat je miste. Hier zijn de cijfers. Dit is wat er via ons systeem binnenkwam. Laten we praten over hoe we dit structureel verdelen."

- Data als bewijs presenteren
- Van CONTROL naar GROWTH is een logische stap, niet een verkoopmoment
- De data verkoopt zichzelf

## Cross-Skill Connecties

| Waar | Connectie |
|---|---|
| tracking-architectuur | Technische delivery van INSTALL + CONTROL. Beexy Pixel, sGTM, consent, CAPI. |
| meta-ads | Campagne-management als onderdeel van het systeem. Ads zijn het kanaal, niet het product. |
| analytics-feedback | Data → diagnose → optimalisatie. Wordt krachtiger met Revenue Control data. |
| partner-comms | Klantcommunicatie over tracking-status, milestones, weekly data audits. |
| shared-kernel | Revenue Control System IS het aanbod. Alle andere skills leveren eraan. |

## Wanneer Laden

```
Klantgesprek over pricing → ALTIJD
Offerte / voorstel schrijven → ALTIJD
Tracking uitleggen aan klant → Gebruik de pitch, niet de techniek
Performance fee bespreken → Variant A/B/C + baseline-vereiste
Upsell van retainer naar RCS → Stap 4 (data als bewijs)
```

## Wanneer NIET Laden

- Bij technische implementatie (dan: tracking-architectuur)
- Bij content-productie (dan: content-skills)
- Bij ad-analyse (dan: analytics-feedback)
