# Violation Patterns — Lookup Tabel

Snelle lookup voor triggers in Nederlandse ad copy. Per patroon: categorie + severity + rewrite-tactiek. Gebruik dit als scan-laag direct na de Niche Deepdive — hier zitten de meest voorkomende exact-match patronen.

## Hoe te gebruiken

1. Scan de tekst op elke patroon-string.
2. Bij hit: noteer severity + categorie.
3. Pas rewrite-tactiek toe.
4. Her-scan de rewrite om te zorgen dat je geen nieuwe trigger introduceert.

---

## Patroon 1 — "Voel jij je…"

| Veld | Waarde |
|---|---|
| **Triggers** | "voel jij je", "voel je je", "voelt je X", "hoe voel jij je" |
| **Categorie** | Personal Attributes (+ Health als er een emotie/conditie volgt) |
| **Severity** | ⚠️ REJECT standaard, ❌ BAN-RISK bij medische conditie in de zin |
| **Rewrite** | Herformuleer naar 3e persoon algemeen: "Veel [doelgroep] ervaren / herkennen / kennen…" |
| **Voorbeeld** | "Voel jij je uitgeput?" → "Uitputting is veel ondernemers niet vreemd." |

---

## Patroon 2 — "Ben jij [conditie/identiteit-kwetsbaar]?"

| Veld | Waarde |
|---|---|
| **Triggers** | "ben jij een [X]", "ben jij iemand die", "ben je X" — waar X kwetsbaarheid impliceert |
| **Categorie** | Personal Attributes |
| **Severity** | ⚠️ REJECT, ❌ BAN-RISK bij beschermde attributen (gezondheid, religie, ras, etc.) |
| **Rewrite** | Reframe als beschrijving van de groep ("Voor [doelgroep] die…") of een eigenschap-observatie ("[Doelgroep] herkennen vaak dat…") |
| **Voorbeeld** | "Ben jij een HSP?" → "Voor hoogsensitieve mensen die hun werkdag willen beschermen." |

---

## Patroon 3 — "Worstel jij met…"

| Veld | Waarde |
|---|---|
| **Triggers** | "worstel jij", "kamp jij met", "heb jij last van", "zit jij vast met" |
| **Categorie** | Personal Attributes + (meestal) Health/Mental Health |
| **Severity** | ❌ BAN-RISK bij medische/psychische conditie, ⚠️ REJECT bij generieke pijn |
| **Rewrite** | "Veel [doelgroep] kennen [pijn]" of "[Pijn] is vaak hardnekkig omdat…" |
| **Voorbeeld** | "Worstel jij met angst?" → "Angstklachten zijn hardnekkiger dan veel mensen denken." |

---

## Patroon 4 — Cureer-claims ("genees/elimineer/verlos")

| Veld | Waarde |
|---|---|
| **Triggers** | "genees", "cureer", "elimineer", "verlos je van", "definitief weg", "voor altijd van je af", "verdwijnt" |
| **Categorie** | Health / Unapproved Medical Claim |
| **Severity** | ❌ BAN-RISK bij medische/psychische conditie, ⚠️ REJECT bij generieke klacht |
| **Rewrite** | Vervang uitkomst-werkwoord door methode-werkwoord: "leer omgaan met", "ontdek hoe je", "begrijp de patronen achter" |
| **Voorbeeld** | "Elimineer je angst in 8 weken" → "Ontdek in 8 weken welke patronen angst voeden." |

---

## Patroon 5 — Tijdgebonden resultaat-belofte

| Veld | Waarde |
|---|---|
| **Triggers** | "binnen X dagen/weken/maanden [uitkomst]", "in X weken van je [probleem] af", "na X dagen [resultaat]" |
| **Categorie** | Misleading Claim + (context-afhankelijk) Health of Financial |
| **Severity** | ⚠️ REJECT, ❌ BAN-RISK bij mental health of gegarandeerd financial |
| **Rewrite** | Reframe tijd als leerperiode, niet uitkomst-garantie: "In X weken leer je [methode]" of "X weken trainen met [aanpak]" |
| **Voorbeeld** | "Binnen 30 dagen burn-out-vrij" → "30 dagen werken met een methode die ondernemers energie teruggeeft" |

---

## Patroon 6 — Specifiek bedrag als belofte

| Veld | Waarde |
|---|---|
| **Triggers** | "€[bedrag] per maand", "jouw eerste €[bedrag]", "verdien €[bedrag]", "[bedrag]k in [tijd]", "6-figure", "7-figure" |
| **Categorie** | Misleading Financial Claim / Unacceptable Business Practices |
| **Severity** | ⚠️ REJECT, ❌ BAN-RISK bij combinatie met "gegarandeerd" of tijdgarantie |
| **Rewrite** | Refame bedrag als input ("voor coaches die €X willen behalen") of schrap geheel ten gunste van methode-beschrijving |
| **Voorbeeld** | "Verdien €10.000/maand" → "Voor coaches met €10k+ maandambitie: het sales-systeem dat past" |

---

## Patroon 7 — "Gegarandeerd" / absolute claims

| Veld | Waarde |
|---|---|
| **Triggers** | "gegarandeerd", "100%", "altijd", "zeker", "nooit meer", "bewezen", "klinisch bewezen" (zonder bron) |
| **Categorie** | Misleading Claim |
| **Severity** | ⚠️ REJECT, ❌ BAN-RISK bij health of financial |
| **Rewrite** | Vervang door zachter alternatief ("consistent", "in de praktijk zien we", "vaak") of schrap zonder verlies van betekenis |
| **Voorbeeld** | "Gegarandeerd 3 klanten in 2 weken" → "De acquisitie-aanpak die coaches binnen 2 weken toepassen" |

---

## Patroon 8 — Identiteit-switch transformatie

| Veld | Waarde |
|---|---|
| **Triggers** | "word een ander mens", "word wie je echt bent", "word het beste versie van jezelf", "nooit meer dezelfde", "complete transformatie" |
| **Categorie** | Transformatie-Belofte + (context) Health |
| **Severity** | 🟡 FLAG buiten health-context, ⚠️ REJECT bij health/weight/mental |
| **Rewrite** | Reframe naar proces-beschrijving: "Bouw [nieuwe gewoonte/aanpak]", "Ontwikkel [vaardigheid]" |
| **Voorbeeld** | "Word een ander mens in 30 dagen" → "30 dagen werken aan één nieuwe gewoonte die blijft" |

---

## Patroon 9 — Voor/na-retoriek in tekst

| Veld | Waarde |
|---|---|
| **Triggers** | "van [negatief] naar [positief]" — **in combinatie met** health/weight/appearance context |
| **Categorie** | Transformatie + (context) Health / Negative Self-Perception |
| **Severity** | 🟡 FLAG buiten health, ⚠️ REJECT in health/weight/mental, ❌ BAN-RISK bij visuele voor/na-beelden |
| **Rewrite** | Beschrijf het traject niet als contrast-switch maar als geleidelijke ontwikkeling: "Hoe [doelgroep] [nieuwe vaardigheid] opbouwen" |
| **Voorbeeld** | "Van uitgeput naar onverslaanbaar" → "Hoe ondernemers hun energie-niveau herstellen" |

---

## Patroon 10 — Body shame / Negative Self-Perception

| Veld | Waarde |
|---|---|
| **Triggers** | "lelijk(e)", "je dijen/buik/gezicht/rimpels", "niemand vertelt je dat je X bent", "je ziet er X uit" |
| **Categorie** | Negative Self-Perception / Objectionable Content |
| **Severity** | ❌ BAN-RISK in health/cosmetic context |
| **Rewrite** | Verwijder persoonlijke afbraak. Beschrijf het probleem neutraal of behavioral: "Waarom [klacht] hardnekkig is" |
| **Voorbeeld** | "Het lelijke geheim achter je buik" → "Waarom buikvet hardnekkig is — inzichten uit [vakgebied]" |

---

## Patroon 11 — Fear-mongering / ramp-voorspelling

| Veld | Waarde |
|---|---|
| **Triggers** | "als je dit niet doet, [ramp]", "je loopt een ramp tegemoet", "over X jaar ben je [ondergang]" |
| **Categorie** | Sensational / Deceptive Practices |
| **Severity** | ⚠️ REJECT, ❌ BAN-RISK bij overdreven of ongefundeerd |
| **Rewrite** | Urgentie zonder ramp-predictie: "Wat nu beslist hoe [doelgroep] er over X jaar voor staat" |
| **Voorbeeld** | "Als je dit niet doet, ben je over 5 jaar blut" → "De beslissing die bepaalt hoe ondernemers de komende 5 jaar staan" |

---

## Patroon 12 — Vergelijkend vernederen

| Veld | Waarde |
|---|---|
| **Triggers** | "terwijl anderen [succes], zit jij nog [faal]", "iedereen behalve jij", "je valt achter" |
| **Categorie** | Negative Self-Perception |
| **Severity** | ⚠️ REJECT |
| **Rewrite** | Vergelijking blijft mogelijk, maar de lezer mag niet persoonlijk als loser gelabeld worden: "Sommige ondernemers groeien harder — niet omdat ze slimmer zijn, maar omdat ze één ding anders doen" |
| **Voorbeeld** | "Terwijl zij 6-figure draaien, ploeter jij nog" → "Waarom sommige coaches sneller opschalen — het is niet talent" |

---

## Patroon 13 — Clickbait "geheim / ze willen niet dat je weet"

| Veld | Waarde |
|---|---|
| **Triggers** | "het geheim van", "wat ze je niet vertellen", "de waarheid achter", "verborgen methode" |
| **Categorie** | Deceptive Practices (risico, niet per se fataal) |
| **Severity** | 🟡 FLAG bij goated-ads ook al verboden als copywriting-woord — hier meer context-afhankelijk |
| **Rewrite** | Vervang door concreet mechanisme: "De methode die coaches gebruiken voor…", "Wat [vakgebied] leert over…" |
| **Voorbeeld** | "Het geheim van 6-figure coaches" → "Hoe 6-figure coaches hun aanbod structureren" |

---

## Patroon 14 — Impliciete kennis van privé-info

| Veld | Waarde |
|---|---|
| **Triggers** | "ik zie dat je…", "ik weet dat je…", "ik herken dat je…" gecombineerd met attribuut |
| **Categorie** | Personal Attributes |
| **Severity** | ⚠️ REJECT |
| **Rewrite** | Vervang door algemene observatie: "In de praktijk zie ik vaak…" of "Coaches herkennen vaak…" |
| **Voorbeeld** | "Ik zie dat je worstelt met je positionering" → "In de praktijk zie ik veel coaches vastlopen op positionering" |

---

## Cross-Pattern Rules

1. **Negatie helpt niet.** "Je bent niet depressief" triggert alsnog Personal Attributes + Mental Health. Verwijder de conditie-naam, niet de bewering.
2. **Vraagvorm helpt niet.** Een vraag als "Voel jij je…?" is even problematisch als een stelling. Vraag = nog steeds assertie.
3. **Numbers liegen niet.** Vervang specifiek bedrag door range of schrap hem — dat is de enige veilige weg.
4. **Vervanging `jij → je` helpt niet.** Beide zijn 2e persoon direct adres. Ga naar 3e persoon of algemeen.
5. **Na elke rewrite: her-scan.** Een rewrite kan een nieuwe trigger introduceren. Cascade-check tot ✅.
