# Winst OS Context — Project-Specifieke Referentie

Specifiek voor het Winst OS platform. Laden wanneer er aan dit project gewerkt wordt.

## Platform Overzicht

**Winst OS** is het Decision & Governance Infrastructure platform van Winstarchitect. Het is het centrale besturingssysteem waarmee partners worden beheerd, funnels worden gemonitord, en data-gedreven beslissingen worden genomen.

## Tech Stack

| Laag | Technologie |
|---|---|
| Frontend | React 18, Vite, TypeScript, Tailwind CSS, shadcn/ui |
| Backend | Supabase (PostgreSQL, Auth, Edge Functions, Storage) |
| Hosting | Lovable Cloud |
| Payments | Mollie, Stripe |
| Integraties | Akiflow (via Zapier), Fireflies, Meta CAPI |
| Monitoring | Interne observability via edge functions |

## Codebase Structuur

```
src/
├── components/     (200+ componenten)
├── hooks/          (130+ custom hooks)
├── pages/          (50+ pagina's)
├── integrations/   (Supabase client, types, edge functions)
├── utils/          (helpers, formatters)
├── contexts/       (React contexts)
└── types/          (TypeScript types)

supabase/
├── functions/      (120+ edge functions)
├── migrations/     (database migraties)
└── config.toml
```

## Kritieke Naming Conventions

| Correct | FOUT | Reden |
|---|---|---|
| `partnerships` | `partners` | Tabel = partnerships, nooit partners |
| `void logOpsRun()` | `await logOpsRun()` | Observability nooit awaiten |
| Winstarchitect | Focusformule | Oude branding, nooit gebruiken |
| Bulletproof META System | — | Verouderde branding, niet refereren |

## Factory vs. Product Mapping

### Factory (stabiel — verandert zelden)
- Database schema's en RLS policies
- Edge function configuraties
- Auth flows en role definitions
- UI component library
- Supabase config

### Product (variabel — verandert per run/klant)
- Partnership data
- Funnel metrics per partner
- Campagne resultaten
- Gebruiker-specifieke dashboards
- Rapporten en analyses

**Regel:** Als je herhaaldelijk Product-data corrigeert, check of de Factory (schema, RLS, edge function) correct is.

## Rol van de Architect

Rick Bazuin (Winstarchitect) is architect en beslisser. NOOIT operationeel.

**Constraints:**
- Max 5 calls per week
- Moet volledig op vakantie kunnen zonder dat het systeem stopt
- Alle operationele taken zijn gedelegeerd of geautomatiseerd
- Beslissingen worden genomen op basis van data, niet onderbuikgevoel

**Communicatie-hiërarchie:**
1. Dashboard metrics (async, dagelijks)
2. Alerts alleen bij kritieke issues (automatisch)
3. Async berichten voor updates (Slack/chat)
4. Calls alleen voor strategische beslissingen

## Doelgroep & Scale

- **Huidige fase:** 50-200 partners
- **Doelstelling:** Schaalbaar naar 1000+ partners zonder lineaire teamgroei
- **Klantprofiel:** Coaches en kennisondernemers, €2k-€15k maandelijks ad spend
- **Service model:** Premium consulting, max 20-25 actieve klanten tegelijk

## Integratie-Specifics

### Meta CAPI
- Server-side event tracking
- Deduplicatie met browser pixel
- Custom events per funnel-stap

### Mollie / Stripe
- Webhooks voor payment status
- Automatische facturatie
- Subscription management

### Akiflow (via Zapier)
- Taak-creatie vanuit platform events
- Deadline tracking
- Prioritering op basis van partner-fase

### Fireflies
- Meeting transcripties automatisch opgeslagen
- Gekoppeld aan partnership records
- Doorzoekbaar voor context bij follow-ups

## Database Kernregels

1. **RLS op ELKE tabel** — geen uitzonderingen
2. **Soft deletes** — nooit hard deleten, altijd `deleted_at` timestamp
3. **Audit trail** — wie heeft wat wanneer gewijzigd
4. **Cascading updates** — relaties via foreign keys, niet applicatie-logica
5. **Indexing** — op elke kolom die in WHERE of JOIN gebruikt wordt
6. **Migraties** — altijd via Supabase migrations, nooit handmatig in de console

## Deployment & Environments

```
Development → Staging → Production

Development: Lokaal of feature branch
Staging: Supabase staging project + Lovable preview
Production: Supabase production + Lovable production

Regel: Nooit direct naar production. Altijd via staging.
```

## Monitoring & Alerting

| Metric | Threshold | Alert |
|---|---|---|
| Edge function errors | >5 per uur | Slack alert |
| Auth failures | >10 per uur | Slack alert + email |
| Database response time | >2 seconden | Dashboard warning |
| Payment webhook failures | >0 | Onmiddellijk alert |
| Uptime | <99.5% | Escalatie naar architect |
