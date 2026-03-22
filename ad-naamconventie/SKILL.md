---
name: ad-naamconventie
description: >
  Standaardiseert ad-namen voor Meta Ads naar het Flywheel OS format: [Format] - [Hook] - [Angle] - [Variant].
  Converteert vrije tekst, batch-hernoemt bestaande ads, valideert namen, en genereert iteratie-varianten.
  Trigger bij: ad naam, naamconventie, hernoem ads, rename, ad naming, naamgeving, creative benoemen,
  ad benoemen, naam voor ad, hoe noem ik mijn ad, batch rename, Meta ad namen, Flywheel OS namen,
  nieuwe variant naam, iteratie naam, v2 maken, A/B naam. Ook triggeren wanneer iemand een ad-concept
  beschrijft en een gestandaardiseerde naam nodig heeft voor Meta Ads Manager of Flywheel OS.
  NIET triggeren bij: ad copy schrijven (goated-ads), ad performance analyseren (analytics-feedback),
  campagne structuur (winst-os).
---

# Ad Naamconventie — Flywheel OS Standard

Standaardiseert ad-namen zodat Flywheel OS patronen kan herkennen, half-life curves kan groeperen,
iteraties kan tracken, en combinatie-intelligence kan berekenen.

## Context Loading

| Nodig | Bron | Wanneer |
|---|---|---|
| Volledige conventie + voorbeelden | `references/conventie-compleet.md` | ALTIJD |

## Het Format

```
[Format] - [Hook] - [Angle] - [Variant]
```

Separator: ` - ` (spatie-streepje-spatie). Altijd 4 segmenten. Altijd dezelfde volgorde.

## Segment 1: Format (verplicht)

| Code | Betekenis | Flywheel OS `format_tag` |
|---|---|---|
| `TH` | Talking Head | TALKING_HEAD |
| `UGC` | User Generated Content | TESTIMONIAL* |
| `Static` | Statische afbeelding | STATIC |
| `Carousel` | Carousel (meerdere slides) | CAROUSEL |
| `Demo` | Product demonstratie | DEMONSTRATION |
| `Testi` | Testimonial / review | TESTIMONIAL* |

*\*UGC en Testi delen dezelfde `TESTIMONIAL` format_tag in Flywheel OS. Het systeem onderscheidt ze niet op database-niveau — het verschil zit in de ad-naam voor menselijke herkenning.*
| `Story` | Storytelling / narratief | STORY |
| `Faceless` | Geen gezicht, voice-over/tekst | FACELESS |
| `Edu` | Educatief / how-to | EDUCATIONAL |

## Segment 2: Hook (verplicht)

Korte beschrijving van de opening in 2-4 woorden. Dit is de menselijk leesbare versie van de hook.

**Awareness mapping (voor Flywheel OS `hook_type` classificatie):**

| Hook-patroon | Awareness Level | Voorbeelden |
|---|---|---|
| Nieuwsgierigheid, open vragen, "wist je dat" | L1_CURIOSITY | `Wist je dat`, `Dit verandert alles`, `3 dingen die` |
| Pijnpunt benoemen, probleem centraal | L2_PAIN | `Pijn opener`, `Moe van`, `Waarom het faalt`, `Stil lijden` |
| Oplossing/belofte tonen, resultaat centraal | L3_PROMISE | `Zo werkt het`, `Het geheim van`, `In 30 dagen` |
| Bewijs, autoriteit, social proof | L4_PROOF | `436 klanten`, `Review klant`, `Case study`, `Resultaten` |
| Direct aanbod, urgentie, FOMO | L5_OFFER | `Laatste kans`, `Nu beschikbaar`, `50% korting`, `Lineup teaser` |

## Segment 3: Angle (verplicht)

De overtuigingsstrategie of emotionele driver.

| Code | Betekenis |
|---|---|
| `FOMO` | Fear of missing out |
| `Social` | Sociaal bewijs |
| `Urgentie` | Tijdsdruk / schaarste |
| `Autoriteit` | Expert positioning |
| `Pijn` | Pijnpunt aanspreken |
| `Aspiratie` | Gewenste uitkomst tonen |
| `Curiosity` | Nieuwsgierigheid opwekken |
| `Prijs` | Prijs/waarde vergelijking |
| `Exclusief` | Exclusiviteit / VIP gevoel |
| `Community` | Erbij horen / tribe |

## Segment 4: Variant (verplicht)

| Code | Betekenis |
|---|---|
| `v1` | Eerste versie |
| `v2`, `v3`... | Iteratie (andere edit/copy/visual) |
| `A`, `B` | A/B test variant |

## Creative Category (verplicht bij aanmaak in Execution Board)

Elke ad krijgt naast Format, Hook en Angle ook een **Creative Category** die bepaalt hoe het Pack-systeem en de Scorecard de creative behandelen.

| Category | Code | Percentage doel | Wanneer kiezen |
|---|---|---|---|
| **Winner Reuse** | `WINNER_REUSE` | 70% van je ads | Bewezen hook/format hergebruikt. De ad is gebaseerd op een winner uit de Winner Vault — zelfde concept, kleine aanpassingen. |
| **Winner Adjacent** | `WINNER_ADJACENT` | 20% van je ads | Winnend patroon uit een andere niche of campagne aangepast. Bijv. een Pain-hook die werkte voor een food festival, vertaald naar jouw muziekfestival. Zelfde emotionele trigger, ander publiek. |
| **Wild Card** | `WILD_CARD` | 10% van je ads | Experiment. Nieuw concept zonder referentie. Puur om nieuwe combinaties te ontdekken die de Intelligence kan leren. |

**Hoe het de iteratie-strategie beïnvloedt:**
- `WINNER_REUSE` iteraties (v2, v3) zijn swap-varianten op bewezen winners → laag risico, verwachte performance
- `WINNER_ADJACENT` zijn cross-niche transplantaties → middel risico, potentieel nieuwe winnaars
- `WILD_CARD` heeft geen parent → als het Patroon A scoort, wordt het de basis voor toekomstige WINNER_REUSE ads

**In de ad-naam:** de category staat niet in de naam. Het wordt apart getagd in het Execution Board bij het aanmaken van de creative.

## Operaties

### 1. Vrije tekst → Gestandaardiseerde naam

Input: beschrijving van een ad-concept.
Output: gestandaardiseerde naam + Flywheel OS metadata.

**Voorbeeld:**
- Input: "Een talking head video waar ik begin met de pijn dat festivals altijd uitverkocht zijn voordat je het doorhebt, met een FOMO angle"
- Output:
  ```
  Naam:       TH - Altijd uitverkocht - FOMO - v1
  format_tag: TALKING_HEAD
  hook_type:  L2_PAIN
  angle:      FOMO
  category:   WILD_CARD (eerste versie, geen referentie)
  ```

### 2. Batch rename

Input: lijst van bestaande ad-namen (uit Meta export).
Output: gestandaardiseerde namen + mapping tabel.

**Voorbeeld:**
- Input: `Ad 1 - festival maart`, `Copy test FOMO`, `Nieuwe video testimonial`
- Output:

| Origineel | Nieuw | format_tag | hook_type |
|---|---|---|---|
| Ad 1 - festival maart | Static - Festival maart - Urgentie - v1 | STATIC | L5_OFFER |
| Copy test FOMO | Static - Copy test - FOMO - v1 | STATIC | L1_CURIOSITY |
| Nieuwe video testimonial | UGC - Testimonial - Social - v1 | TESTIMONIAL | L4_PROOF |

Wanneer de originele naam onvoldoende informatie bevat, vraag door. Raad niet.

### 3. Validatie

Input: ad-naam.
Output: geldig/ongeldig + correctiesuggestie.

**Checks:**
- Exact 4 segmenten gescheiden door ` - `
- Segment 1 is een geldig Format-code
- Segment 3 is een geldig Angle-code
- Segment 4 is een geldig Variant-code (v[n] of [A-Z])
- Geen campagnenaam in de ad-naam
- Geen datums in de ad-naam
- Consistente afkortingen (niet `TalkingHead` en `TH` door elkaar)

### 4. Iteratie-naam genereren

Input: bestaande ad-naam + welke dimensie is geswapped.
Output: nieuwe naam met verhoogd variant-nummer + `iteration_swaps` metadata.

**Voorbeeld:**
- Input: `TH - Pijn opener - FOMO - v1` + swap: HOOK
- Output:
  ```
  Naam:             TH - Altijd uitverkocht - FOMO - v2
  parent:           TH - Pijn opener - FOMO - v1
  iteration_swaps:  [HOOK]
  ```

- Input: `TH - Pijn opener - FOMO - v1` + swap: MODEL + VISUAL_STYLE
- Output:
  ```
  Naam:             TH - Pijn opener - FOMO - v2
  parent:           TH - Pijn opener - FOMO - v1
  iteration_swaps:  [MODEL, VISUAL_STYLE]
  ```

Let op: als alleen MODEL of VISUAL_STYLE is geswapped (niet de hook), blijft de naam gelijk behalve het variant-nummer. De swap wordt gelogd in de metadata, niet in de naam. Een ander format of angle is geen iteratie maar een nieuw concept (→ v1 zonder parent).

### 5. Pack-namen genereren

Input: Blueprint pack-schema (uit Campaign Planner).
Output: volledige set ad-namen per pack met correcte variant-nummering.

**Voorbeeld:**
- Input: Pack P1 bevat 4 ads: 2× L2_PAIN + TESTIMONIAL, 1× L4_PROOF + DEMO, 1× WILD_CARD
- Output:
  ```
  P1:
    UGC - [hook tbd] - [angle tbd] - v1
    UGC - [hook tbd] - [angle tbd] - v2
    Demo - [hook tbd] - [angle tbd] - v1
    [format tbd] - [hook tbd] - [angle tbd] - v1  ← Wild Card
  ```

Bij `[tbd]` velden: vraag de strateeg om de hook en angle in te vullen. Genereer geen placeholder-namen die er uitzien als echte namen.

## Harde Regels

1. **Altijd 4 segmenten** — ook als je denkt dat het overbodig is
2. **Consistent binnen één campagne** — mix niet `TalkingHead` en `TH`
3. **Geen spaties in segment-codes** — gebruik underscore als nodig (`Voor_en_na`)
4. **Geen campagnenaam in de ad-naam** — Meta toont die al apart
5. **Geen datums** — Meta heeft rapportageperiodes
6. **Hook in menselijke taal** — geen codes, maar leesbare beschrijving van 2-4 woorden
7. **Angle in code** — gebruik de gestandaardiseerde codes uit de tabel
8. **Variant begint altijd bij v1** — niet bij v0
9. **Bij twijfel: vraag door** — raad geen format, hook of angle als de input onduidelijk is

## Flywheel OS Koppeling

De ad-naam in Meta Ads Manager wordt door de CSV-import ingelezen als `ad_name` in `week_data`.
Het systeem gebruikt de naam voor:

| Systeem-onderdeel | Leest segment | Wat het doet |
|---|---|---|
| Half-life curves | Format (segment 1) | Groepeert decay per format-type |
| Iteratie-tracking | Variant (segment 4) | Herkent v1→v2 als parent-child |
| Pattern Library | Hook + Format | Bouwt combinatie-heatmap |
| Creative Intelligence | Alle segmenten | Format×Hook×Angle rankings |
| Pack-analyse | Variant | Groepeert A/B resultaten |

De `format_tag`, `hook_type` en `creative_category` worden apart opgeslagen in `execution_items` — niet afgeleid uit de naam. De naam is voor menselijke leesbaarheid en patroonherkenning; de metadata is voor systeem-berekeningen.
