# Open Vragen Template — Tracking Intake

Gebruik dit bij elk nieuw tracking-project. Groepeer vragen per fase. Pas klantnaam en specifics aan.

## Fase 1 — Blokkeert de start

| # | Vraag | Actie voor klant |
|---|-------|-----------------|
| OQ-4 | Bestaande GTM-container? | Open CF2.0 → Site Settings → Head Code. Zoek naar GTM-XXXXXXX. Stuur het container-ID. |
| OQ-6 | Facebook Access Token in CF2.0? | Open CF2.0 → Site Settings → Tracking Code. Screenshot van huidige inhoud (Access Token aanwezig? Facebook Pixel ingeschakeld?). |
| OQ-10 | WinstArchitect cookiebanner al actief? | Bevestig of de banner al wordt gebruikt op een andere site. Zo ja: stuur configuratie. Zo niet: wij richten in. |

## Fase 2 — Nodig voor attributie

| # | Vraag | Actie voor klant |
|---|-------|-----------------|
| OQ-1 | Calendly-abonnement? | Calendly → Account Settings → Billing. Zapier-koppeling vereist Standard of hoger. |
| OQ-2 | Airtable-kolomstructuur? | Screenshot of overzicht van huidige kolomnamen in de Leads-tabel. |
| OQ-3 | Zapier-account en -abonnement? | E-mailadres account, actieve Calendly→Airtable-zap aanwezig? Huidig abonnement. Multi-stap zaps vereisen Starter of hoger. |
| OQ-5 | Meta CAPI Access Token? | Meta BM → Events Manager → Data Sources → Pixel → Settings → Conversions API. Stuur token of bevestig dat er nog geen is. |
| OQ-9 | Calendly: widget of redirect? | Klik op de Calendly-knop: verschijnt een widget in de pagina (inline embed) of navigeert de browser naar calendly.com (redirect)? |
| OQ-11 | Zapier: multi-stap zaps beschikbaar? | Bevestig Zapier-abonnement. Starter of hoger vereist voor fbclid-extractie via Formatter. |

## Fase 3 — Nodig voor server-side

| # | Vraag | Actie voor klant |
|---|-------|-----------------|
| OQ-7 | DNS-beheer voor domein? | Bevestig de registrar (bijv. TransIP, GoDaddy, Cloudflare). We moeten een CNAME aanmaken voor t.{domein}.com. |
| OQ-8 | Vimeo embed-code? | Paginabron bekijken → zoek op "vimeo". Stuur de volledige src-waarde van de iframe inclusief query parameters. |

## Instructies bij gebruik

1. Kopieer de relevante vragen naar het tracking-voorstel
2. Pas klantnaam, domeinnaam en pixel-ID aan
3. Markeer Fase 1-vragen als **urgent — blokkeert de start**
4. Voeg toe: "De overige vragen kunnen later worden aangeleverd voor Fase 2 en 3"
5. Voeg altijd de meest urgente actie toe (Access Token verwijderen) met stap-voor-stap instructies
