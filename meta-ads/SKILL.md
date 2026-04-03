---
name: meta-ads
description: >
  META Ads campagnemanagement voor B2C coaches, therapeuten, kennisondernemers.
  EXCLUSIEF: campagne-architectuur, targeting, budget, Advantage+, lead form ads,
  retargeting, pixel/CAPI, scaling. Trigger bij: campagne opzetten, Meta Ads Manager,
  targeting, budget verdelen, Advantage+, scaling ads, CPL/ROAS, retargeting, lookalike,
  lead form ads, ad account structuur, pixel, CAPI, cold/warm/hot traffic.
  NIET: ad copy (goated-ads), analyse (analytics-feedback), pagina's (funnel-pages),
  scripts (funnel-scripts), webinar content (core-story-webinar), nurture sequences
  (shared-kernel), revenue plays (shared-kernel).
---

# META Ads Campagne Engine

## Afbakening

| Vraag | Route |
|---|---|
| Campagne opzetten | **meta-ads** |
| Ad copy/hooks | goated-ads |
| Ad analyse | analytics-feedback |
| Show rate/nurture | shared-kernel → lead-nurture-protocol |
| Revenue play | shared-kernel → campaign-plays |
| Pagina's | funnel-pages |
| Ad namen | ad-naamconventie |

## Context Loading

| Bron | Wanneer |
|---|---|
| `references/campaign-architectuur.md` | ALTIJD |
| `references/top-10-bronnen.md` | Research, partner educatie |
| `references/meta-platform-updates.md` | Advantage+, compliance |
| `shared-kernel/references/lead-nurture-protocol.md` | Show rate (SSOT) |
| `shared-kernel/references/campaign-plays.md` | Play-selectie (SSOT) |
| `shared-kernel/references/doelgroep-mind-mining.md` | Targeting-strategie |
| `shared-kernel/references/niche-adaptaties.md` | Eerste campagne/partner |
| `shared-kernel/references/quality-gate.md` | NA opzet |

## 3-Laags Architectuur

| Laag | Budget | Doelgroep | Targeting | Creative |
|---|---|---|---|---|
| COLD | 60-70% | Problem/Solution Aware | Broad + Advantage+ | via goated-ads |
| WARM | 20-30% | Video viewers, page visitors | Custom 1-30d | Proof, testimonials |
| HOT | 5-10% | Abandoners, no-shows | Custom 1-7d | Urgentie, countdown |

## Delivery bij "ZET CAMPAGNE OP"

1. Technische Setup: Pixel, CAPI, events, payment, verification
2. 3-Laags Architectuur: per laag objectief, targeting, budget %, plaatsing
3. Targeting Plan: Advantage+, interests, customs, lookalikes, exclusies
4. Budget Calculator: dagbudget/laag, break-even CPL, scaling triggers
5. Retargeting Cascade: proof → objection-bust → urgentie + timing
6. Creative Brief → route goated-ads: 50 hooks, 5 body's, 3 CTAs
7. Lead Nurture → route shared-kernel: lead-nurture-protocol

## Scaling

**Schaal wanneer:** CPA < break-even 3d | Frequency < 2.5 | CTR > 1% | Hook rate > 25%
**Hoe:** Horizontaal (nieuw publiek) → Verticaal (+20%/3d) → Kaleidoscoop (goated-ads) → Platform-split
**Kill:** CPA > 2× na 1000 impr | CTR < 0.5% na 48u | Freq > 3.5 zonder conversies

## Compliance (Coaches & Therapeuten)

Geen medische claims. Geen before/after. Geen targeting op gezondheid. Disclaimer bij resultaatclaims. Privacy policy bij lead forms. Special Ad Categories checken.

## Quality Gate

☐ Pixel+CAPI geverifieerd ☐ Events correct ☐ 3 lagen compleet ☐ Budget < break-even ☐ Nurture actief (shared-kernel) ☐ Exclusies correct ☐ Compliance OK ☐ Creative brief → goated-ads ☐ Naamconventie → ad-naamconventie ☐ Analytics dashboard → analytics-feedback ☐ Scaling triggers gedefinieerd

## Eigenaarschap

| Eigendom meta-ads | Routeert naar |
|---|---|
| Campagne-structuur, targeting, budget | — |
| Pixel/CAPI, lead forms, retargeting | — |
| Scaling structuur | analytics-feedback (trigger) |
| Ad copy | goated-ads (ontvangt brief) |
| Ad namen | ad-naamconventie |
| Lead nurture | shared-kernel (SSOT) |
| Performance analyse | analytics-feedback |
