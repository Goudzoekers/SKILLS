---
name: meta-policy-guard
description: >
  Verplichte compliance gate voor META/Instagram ads. Legt elke Hook, Body en CTA onder
  de stofkam tegen META Ad Standards voordat iets naar Ads Manager gaat. Afgestemd op
  risico's voor B2C coaches, therapeuten en kennisondernemers: personal attributes,
  health claims, financial outcomes, transformatie-beloftes, sensational content.
  EXCLUSIEF compliance — schrijft geen ads. Trigger bij: policy check, META policy,
  compliance gate, afkeuring risico, ad ban check, voldoet mijn ad, policy violatie,
  stofkam, goedkeuringskans, personal attribute, health claim, voor/na, ad compliance,
  policy audit, ad afgekeurd, account ban, restricted category. Trigger AUTOMATISCH na
  elke goated-ads batch — ongekeurd materiaal verlaat de sessie nooit.
  NIET triggeren bij: ads schrijven (goated-ads), campagne setup (meta-ads),
  analytics (analytics-feedback), pagina copy (funnel-pages).
---

# META Policy Guard — Compliance Gate

Elke ad passeert deze skill voor delivery. Coaches, therapeuten en kennisondernemers zitten vol op de niche-risico's. Deze gate voorkomt dat goede copy sneuvelt op vermijdbare triggers.

## Ecosysteem Positie

```
goated-ads  →  ► meta-policy-guard ◄  →  meta-ads → launch
     ↑                 │
     └─ rewrite-loop ──┘  (bij ❌/⚠️)
```

Geen compliance rapport = geen delivery.

## Context Loading

| Bron | Wanneer |
|---|---|
| `references/niche-risico-deepdive.md` | Elke check — 5 hotspots + voorbeelden |
| `references/meta-policy-foundation.md` | Elke check — breed fundament |
| `references/violation-patterns.md` | Bij hit: trigger → rewrite lookup |
| `references/compliance-rapport-template.md` | Output layout |
| `shared-kernel/references/schrijfregels-nl.md` | NL-conventies in rewrites |

## Stofkam-Workflow

**1. Parse** — split batch in units. Elke Hook/Body/CTA apart, eigen verdict.

**2. Niche-scan** — check `niche-risico-deepdive.md`. 5 hotspots (volledig beschreven in reference):
Personal Attributes · Health/Mental Health · Financial Outcomes · Transformatie-Beloftes · Sensational/Negative Self-Perception.

**3. Fundament-scan** — check `meta-policy-foundation.md`. Misleading claims, deceptive practices, shocking content, misinformation, restricted products, Special Ad Categories.

**4. Classificeer:**

| Severity | Betekenis | Actie |
|---|---|---|
| ❌ BAN-RISK | Herhaling = account-ban | Rewrite verplicht |
| ⚠️ REJECT | Ad wordt afgekeurd | Rewrite aanbevolen |
| 🟡 FLAG | Borderline, context-afhankelijk | Review |
| ✅ PASS | Compliant | Doorlaten |

**5. Rewrite** — voor elke ❌/⚠️: compliant alternatief dat conversie-intent behoudt. Kernprincipe: **behoud emotionele resonantie, verwijder assertie over de persoon.**

Voorbeeld: "Voel jij je uitgeput en futloos?" → ❌ Personal Attribute + Health.
Rewrite: "Veel vrouwen boven de 40 herkennen dit: dagen waarop de fut op lijkt."

**6. Rapport** — output per `compliance-rapport-template.md`.

## Vuistregels

- **Conversie ≠ violatie.** "Jij" → "veel mensen" kost zelden conversie, bespaart bans.
- **Context matters.** Zelfde woord faalt in ad A, werkt in ad B. Check de zin.
- **Bij twijfel: flag, niet pass.** Afkeuring kost meer dan rewrite.
- **Landing page = onderdeel van de ad.** Claimt de pagina wat de ad niet durft? Faal.
- **Therapeuten: zero medische claims.** Ooit.
- **Geld-coaches: reframe naar vaardigheid/methode,** nooit uitkomst-garantie.

## Output

Batch summary (X ✅ / Y 🟡 / Z ⚠️ / W ❌) + per hit (origineel, severity, categorie, trigger, rewrite, behoud-logica) + batch-verdict (GO / CONDITIONAL / NO-GO) + compliant batch ready-to-copy. Layout: `references/compliance-rapport-template.md`.
