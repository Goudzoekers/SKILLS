# Ad Naamconventie — Compleet Referentiebestand

## Format: `[Format] - [Hook] - [Angle] - [Variant]`

---

## Alle Format Codes

| Code | Voluit | Wanneer gebruiken | Flywheel OS format_tag |
|---|---|---|---|
| `TH` | Talking Head | Persoon spreekt naar camera | TALKING_HEAD |
| `UGC` | User Generated Content | Klant/gebruiker maakt de content | TESTIMONIAL |
| `Static` | Statische afbeelding | Enkele afbeelding met tekst | STATIC |
| `Carousel` | Carousel | Meerdere slides/swipe | CAROUSEL |
| `Demo` | Demonstratie | Product in actie, voor/na | DEMONSTRATION |
| `Testi` | Testimonial | Review, quote, getuigenis | TESTIMONIAL |
| `Story` | Storytelling | Narratief, "hoe ik van X naar Y" | STORY |
| `Faceless` | Faceless | Geen gezicht: voice-over, tekst, memes, B-roll | FACELESS |
| `Edu` | Educatief | How-to, uitleg, whiteboard | EDUCATIONAL |

### Wanneer welk format?

| Campagne-fase | Aanbevolen formats | Reden |
|---|---|---|
| Launch (week 1-2) | TH, UGC, Static | Breed testen, snel produceerbaar |
| Cruise (week 3+) | Winners + iteraties | Schaal wat werkt |
| Eindsprint (<14 dagen) | TH, Static, Faceless | FOMO/urgentie, snel te maken |
| Wild Card | Demo, Story, Edu | Experimenteer buiten comfort zone |

---

## Alle Angle Codes

| Code | Betekenis | Werkt goed bij | Awareness |
|---|---|---|---|
| `FOMO` | Fear of missing out | Events, limited edition, seizoensgebonden | L4-L5 |
| `Social` | Sociaal bewijs | Reviews, aantallen, community | L3-L4 |
| `Urgentie` | Tijdsdruk / schaarste | Countdown, laatste X plekken | L5 |
| `Autoriteit` | Expert positioning | Certificaten, ervaring, media | L3-L4 |
| `Pijn` | Pijnpunt aanspreken | Frustratie, gemiste kansen | L2 |
| `Aspiratie` | Gewenste uitkomst | Droomresultaat, lifestyle | L2-L3 |
| `Curiosity` | Nieuwsgierigheid | Open loops, "dit wist je niet" | L1 |
| `Prijs` | Prijs/waarde vergelijking | Aanbiedingen, vergelijkingen | L4-L5 |
| `Exclusief` | Exclusiviteit / VIP | Early access, insider, backstage | L4-L5 |
| `Community` | Erbij horen / tribe | "Sluit je aan bij", gezamenlijk | L3 |

### Angle × Awareness Matrix

```
            L1        L2        L3        L4        L5
           (Unaware) (Problem) (Solution)(Product) (Most Aware)
Curiosity  ████████  ████      ██
Pijn       ██        ████████  ████
Aspiratie            ████████  ████████
Social                         ████████  ████████
Autoriteit                     ████████  ████████
Community                      ████████  ████
FOMO                                     ████████  ████████
Prijs                                    ████████  ████████
Exclusief                                ████████  ████████
Urgentie                                           ████████
```

---

## Awareness Level → Hook Mapping

### L1: Curiosity (Unaware)
De persoon weet niet dat er een probleem of oplossing is. Hook prikkelt nieuwsgierigheid.

**Hook-patronen:**
- `Wist je dat` — open vraag
- `Dit verandert alles` — bold statement
- `3 dingen die` — listicle opening
- `Niemand vertelt je` — insider kennis
- `Waarom iedereen` — social curiosity

**Voorbeeld-namen:**
```
TH - Wist je dat - Curiosity - v1
Faceless - Niemand vertelt je - Curiosity - v1
Static - 3 dingen die - Curiosity - v1
```

### L2: Pain-Driven (Problem Aware)
De persoon kent het probleem maar niet de oplossing. Hook benoemt de pijn.

**Hook-patronen:**
- `Pijn opener` — directe pijn
- `Moe van` — frustratie
- `Waarom het faalt` — falen benoemen
- `Stil lijden` — empathie
- `Elke keer weer` — herkenning

**Voorbeeld-namen:**
```
TH - Pijn opener - Pijn - v1
UGC - Moe van - Aspiratie - v1
Story - Elke keer weer - Pijn - v2
```

### L3: Promise-Driven (Solution Aware)
De persoon kent het probleem en zoekt een oplossing. Hook toont de belofte.

**Hook-patronen:**
- `Zo werkt het` — uitleg
- `Het geheim van` — insider
- `In 30 dagen` — tijdgebonden belofte
- `Stap voor stap` — proces
- `De methode` — systematiek

**Voorbeeld-namen:**
```
Edu - Zo werkt het - Autoriteit - v1
TH - Het geheim van - Social - v1
Demo - In 30 dagen - Aspiratie - v1
```

### L4: Proof-Driven (Product Aware)
De persoon kent de oplossing en overweegt jouw product. Hook toont bewijs.

**Hook-patronen:**
- `436 klanten` — getal als bewijs
- `Review klant` — testimonial
- `Case study` — diepgaand bewijs
- `Resultaten` — voor/na
- `Bekijk zelf` — demonstratie

**Voorbeeld-namen:**
```
Testi - Review klant - Social - v1
Demo - Resultaten - Autoriteit - v1
Carousel - Case study - Social - v1
```

### L5: Offer-Driven (Most Aware)
De persoon is klaar om te kopen. Hook is het aanbod zelf.

**Hook-patronen:**
- `Laatste kans` — urgentie
- `Nu beschikbaar` — beschikbaarheid
- `50% korting` — prijs
- `Lineup teaser` — product reveal (events)
- `Tickets live` — direct aanbod

**Voorbeeld-namen:**
```
Static - Laatste kans - Urgentie - v1
Static - Lineup teaser - FOMO - v1
Faceless - Tickets live - Urgentie - v1
```

---

## Iteratie-regels

### Variant-nummering

| Situatie | Nummering | Voorbeeld |
|---|---|---|
| Eerste versie | `v1` | `TH - Pijn opener - FOMO - v1` |
| Andere edit/cut van dezelfde video | `v2` | `TH - Pijn opener - FOMO - v2` |
| A/B test (tegelijk) | `A`, `B` | `Static - Lineup - FOMO - A` / `B` |
| Compleet nieuw concept | `v1` (nieuwe naam) | `UGC - Wist je dat - Social - v1` |

### Swap-dimensies en naamwijzigingen

| Swap | Verandert de naam? | Voorbeeld |
|---|---|---|
| HOOK (andere opening) | JA — hook segment verandert | `TH - Pijn opener - FOMO - v1` → `TH - Altijd uitverkocht - FOMO - v2` |
| MODEL (ander persoon) | NEE — alleen variant++ | `TH - Pijn opener - FOMO - v1` → `TH - Pijn opener - FOMO - v2` |
| PRODUCT (ander product) | OPTIONEEL — als het de hook verandert | Afhankelijk van context |
| FRAMING (ander camerastandpunt) | NEE — alleen variant++ | `TH - Pijn opener - FOMO - v1` → `TH - Pijn opener - FOMO - v2` |
| BODY_CTA (andere body/CTA) | NEE — alleen variant++ | `TH - Pijn opener - FOMO - v1` → `TH - Pijn opener - FOMO - v2` |
| VISUAL_STYLE (andere editing) | NEE — alleen variant++ | `TH - Pijn opener - FOMO - v1` → `TH - Pijn opener - FOMO - v2` |
| FORMAT (ander format) | JA — format segment verandert | `TH - Pijn opener - FOMO - v1` → `UGC - Pijn opener - FOMO - v1` |
| ANGLE (ander angle) | JA — angle segment verandert | `TH - Pijn opener - FOMO - v1` → `TH - Pijn opener - Pijn - v1` |

### Wanneer begint variant opnieuw bij v1?

Wanneer het Format OF de Hook OF de Angle verandert → nieuw concept → `v1`.
Wanneer alleen Model, Framing, Body/CTA of Visual Style verandert → zelfde concept → variant++.

---

## Veelgemaakte Fouten

| Fout | Waarom fout | Correctie |
|---|---|---|
| `Ad 1 - festival maart` | Geen format, geen angle, datum erin | `Static - Festival maart - FOMO - v1` |
| `TalkingHead - Pijn opener - FOMO - v1` | `TalkingHead` moet `TH` zijn | `TH - Pijn opener - FOMO - v1` |
| `TH - Pijn - FOMO - v1` | Hook te kort, niet beschrijvend | `TH - Pijn opener - FOMO - v1` |
| `TH - Pijn opener - FOMO` | Mist variant (segment 4) | `TH - Pijn opener - FOMO - v1` |
| `TH Pijn opener FOMO v1` | Verkeerde separator (geen ` - `) | `TH - Pijn opener - FOMO - v1` |
| `Campagne X - TH - Pijn opener - FOMO - v1` | 5 segmenten, campagnenaam erin | `TH - Pijn opener - FOMO - v1` |
| `TH - FOMO - Pijn opener - v1` | Verkeerde volgorde (angle voor hook) | `TH - Pijn opener - FOMO - v1` |

---

## Niche-specifieke Voorbeelden

### Events / Festivals

```
TH - Lineup teaser - FOMO - v1
Static - Laatste tickets - Urgentie - v1
UGC - Aftermovie reactie - Social - v1
Carousel - 5 redenen - Aspiratie - v1
Faceless - Countdown - Urgentie - v1
Demo - Backstage tour - Exclusief - v1
Story - Vorig jaar gemist - FOMO - v1
```

### Coaches / High-Ticket

```
TH - Pijn opener - Pijn - v1
UGC - Klantresultaat - Social - v1
Edu - 3 stappen methode - Autoriteit - v1
Testi - Review klant - Social - v1
Static - Gratis masterclass - Prijs - v1
Story - Van burnout naar - Aspiratie - v1
Demo - Sessie fragment - Autoriteit - v1
```

### E-commerce

```
Demo - Voor en na - Aspiratie - v1
UGC - Unboxing - Curiosity - v1
Static - Flash sale - Urgentie - v1
Carousel - Bestsellers - Social - v1
Faceless - Productfeature - Edu - v1
TH - Waarom dit product - Autoriteit - v1
```
