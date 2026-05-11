# Compliance Rapport — Template

De output-structuur voor elke batch die door `meta-policy-guard` gaat. Copieer dit template voor elke delivery en vul in. De rapport-layout is **niet onderhandelbaar**: Flywheel OS en `analytics-feedback` kunnen later op deze structuur bouwen (bv. pattern-aggregatie over klanten).

## Structuur

```
# META Policy Compliance Rapport

**Klant:** [klantnaam]
**Batch-id:** [bv. RF | Pack07 | 2026-04-19]
**Units:** [X hooks / Y body's / Z CTAs = N totaal]
**Verdict:** [GO / CONDITIONAL / NO-GO]
**Datum:** [YYYY-MM-DD]

---

## Summary

- ✅ PASS: [aantal] ([%])
- 🟡 FLAG: [aantal] ([%])
- ⚠️ REJECT: [aantal] ([%])
- ❌ BAN-RISK: [aantal] ([%])

**Batch-verdict:** [GO / CONDITIONAL / NO-GO]
**Toelichting:** [1 zin waarom deze verdict]

---

## Hits

### [❌/⚠️/🟡] Hook/Body/CTA [nummer] — [severity]

**Origineel:**
> [exacte tekst]

**Policy-categorie:** [bv. Personal Attributes + Mental Health]
**Trigger:** [specifieke woorden/frase]
**Waarom:** [1-2 zinnen — welk META-principe wordt geschonden]

**Rewrite:**
> [compliant alternatief]

**Behoud-logica:** [1 zin — wat er aan conversie-intent bewaard blijft]

---

[Herhaal per hit]

---

## Compliant Batch (Ready-to-Submit)

### Hooks ([N] totaal, [aantal] rewrites toegepast)

1. [hook 1 — gerewrite'd waar nodig, ongewijzigd waar PASS]
2. [hook 2]
...

### Body's ([N] totaal, [aantal] rewrites toegepast)

1. [body 1]
2. [body 2]
...

### CTAs ([N] totaal, [aantal] rewrites toegepast)

1. [cta 1]
2. [cta 2]
...

---

## Delivery-Checklist

- [ ] Alle ❌ BAN-RISK units zijn herschreven en opnieuw gecontroleerd tot ✅
- [ ] Alle ⚠️ REJECT units zijn herschreven (aanbevolen)
- [ ] 🟡 FLAG units: beslissing genomen (pass-with-note / rewrite / kill)
- [ ] Landing page gecheckt tegen dezelfde policy-gate
- [ ] Targeting-plan gecheckt met `meta-ads` (geen personal-attribute targeting)
- [ ] Special Ad Category-check (housing/employment/credit?) → `meta-ads`
- [ ] Rapport gearchiveerd voor klantdossier

---

## Batch-verdicts — wanneer welke

| Verdict | Voorwaarde |
|---|---|
| **GO** | 0 ❌, 0 ⚠️. 🟡 FLAG mag met expliciete doorlaat-reden. |
| **CONDITIONAL** | 0 ❌. ⚠️ REJECT aanwezig maar rewrites geleverd — klant of Rick kiest per unit. |
| **NO-GO** | ≥1 ❌ BAN-RISK die niet is herschreven, OF systemische violation-patronen door hele batch. |
```

---

## Voorbeeld — Compact Ingevuld

```
# META Policy Compliance Rapport

**Klant:** Marjolein Visser — Stresscoach
**Batch-id:** MV | Pack03 | 2026-04-19
**Units:** 50 hooks / 5 body's / 3 CTAs = 58 totaal
**Verdict:** CONDITIONAL
**Datum:** 2026-04-19

---

## Summary

- ✅ PASS: 52 (90%)
- 🟡 FLAG: 2 (3%)
- ⚠️ REJECT: 3 (5%)
- ❌ BAN-RISK: 1 (2%)

**Batch-verdict:** CONDITIONAL
**Toelichting:** 1 BAN-RISK hook is herschreven; 3 REJECT-hits hebben alternatieven gekregen. Landing page moet nog gecheckt.

---

## Hits

### ❌ Hook 12 — BAN-RISK

**Origineel:**
> Voel jij je al maanden opgebrand en depressief?

**Policy-categorie:** Personal Attributes + Mental Health (Unapproved Medical Claim)
**Trigger:** "Voel jij je" + "depressief"
**Waarom:** Directe 2e-persoons-assertie over mentale gezondheid (beschermd personal attribute). META-rejection zekerheid; bij herhaling account-restrictie.

**Rewrite:**
> Opgebrand zijn sluipt er in — veel ondernemers merken het pas als het maanden aan de gang is.

**Behoud-logica:** Emotionele resonantie via algemene observatie; lezer herkent zichzelf zonder dat de ad het beweert.

---

### ⚠️ Hook 27 — REJECT

**Origineel:**
> In 8 weken van je stress af — gegarandeerd.

**Policy-categorie:** Health Outcome Claim + Misleading Claim
**Trigger:** "van je [klacht] af" + "gegarandeerd"
**Waarom:** Tijdgebonden health-uitkomst-garantie zonder onderbouwing. Twee triggers die samen rejection forceren.

**Rewrite:**
> 8 weken werken met een methode die stress-patronen doorbreekt.

**Behoud-logica:** Tijdsdaadkracht + concrete belofte van een methode, zonder uitkomst-garantie.

---

### 🟡 Hook 34 — FLAG

**Origineel:**
> Herken jij dit: je voelt je moe voor de dag begint?

**Policy-categorie:** Personal Attributes (borderline)
**Trigger:** "Herken jij" + energie-toestand
**Waarom:** "Jij"-adres met impliciete fysieke toestand. Afhankelijk van review-reviewer kan dit pass of reject zijn. Safer-alternatief beschikbaar.

**Rewrite (optioneel):**
> Veel ondernemers starten de dag al moe — en vragen zich af waarom.

**Behoud-logica:** Zelfde inzicht, zonder 2e-persoons-assertie.

---

## Compliant Batch (Ready-to-Submit)

### Hooks (50 totaal, 4 rewrites toegepast)

1. Het moment waarop je beseft dat harder werken niet meer werkt.
2. [hook 2 — ongewijzigd, PASS]
...
12. [REWRITE] Opgebrand zijn sluipt er in — veel ondernemers merken het pas als het maanden aan de gang is.
...
27. [REWRITE] 8 weken werken met een methode die stress-patronen doorbreekt.
...

### Body's (5 totaal, 0 rewrites)

1. [body 1]
...

### CTAs (3 totaal, 0 rewrites)

1. Klik op de knop hieronder. Plekken beperkt.
...

---

## Delivery-Checklist

- [x] Alle ❌ BAN-RISK units herschreven en opnieuw gecontroleerd tot ✅
- [x] Alle ⚠️ REJECT units herschreven
- [x] 🟡 FLAG units: 1 rewrite voorgesteld, 1 doorgelaten met note
- [ ] Landing page — nog checken met klant
- [x] Targeting-plan gecheckt via `meta-ads`
- [x] Geen Special Ad Category triggers
- [x] Rapport gearchiveerd
```

---

## Rapportage-regels

1. **Gebruik altijd de 4 severities** (✅ 🟡 ⚠️ ❌) — niet versimpelen naar pass/fail.
2. **Benoem ALLE policy-categorieën** die geraakt worden, ook als 1 trigger meerdere policies raakt.
3. **Rewrite verplicht leveren** bij ❌ en ⚠️. Bij 🟡: optioneel aanbieden.
4. **Behoud-logica expliciet schrijven** — dit is waar de rewrite zijn conversie-waarde krijgt.
5. **Landing page blijft buiten scope** van deze skill, maar de checklist herinnert aan de externe check.
6. **Archief per klant** — rapporten bewaren maakt pattern-learning mogelijk in `analytics-feedback`.
