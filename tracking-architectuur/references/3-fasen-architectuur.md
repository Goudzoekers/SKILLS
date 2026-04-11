# 3-Fasen Tracking Architectuur — Volledige Specificatie

Referentiedocument met alle scripts, configuraties en veldkoppelingen per fase. Lees dit ALTIJD bij tracking-gerelateerde implementatie.

---

## Fase 1 — Fundament: GTM + Consent + fbclid-capture

### A — GTM in CF2.0 Head Code

GTM wordt geïnjecteerd via ClickFunnels Site Settings → Head Code. Standaard GTM-snippet met container-ID.

**Locatie:** CF2.0 → Site & Blog → [sitenaam] → Settings → Head Code
**Vereist:** GTM container-ID (GTM-XXXXXXX) — opvragen bij klant (OQ-4)

### B — Consent Mode v2 Initialisatie

Een GTM Custom HTML-tag stelt vóór enige andere tag alle toestemmingssignalen in op "geweigerd". Deze tag heeft de hoogste prioriteit en vurt op All Pages.

```javascript
gtag('consent', 'default', {
  'ad_storage': 'denied',
  'analytics_storage': 'denied',
  'ad_user_data': 'denied',
  'ad_personalization': 'denied',
  'wait_for_update': 500
});
```

Alle Meta Pixel-tags in GTM wachten op dit signaal en vuren pas nadat de gebruiker toestemming heeft gegeven.

### C — WinstArchitect Cookiebanner

De WinstArchitect cookiebanner (whitelabel-oplossing Voxxy Creative Lab) biedt:
- Kant-en-klare Consent Mode v2-integratie
- Nederlandstalige banners conform AP-eisen
- Gelijke weergave "Alles accepteren" en "Alles weigeren"
- Laadt via GTM

Wanneer een bezoeker akkoord gaat:
```javascript
gtag('consent', 'update', {
  'ad_storage': 'granted',
  'analytics_storage': 'granted',
  'ad_user_data': 'granted',
  'ad_personalization': 'granted'
});
```

**Status opvragen bij klant (OQ-10):** Wordt de banner al gebruikt op een andere site?

### D — fbclid Capture Tag

GTM Custom HTML-tag, alle pagina's, vóór toestemming (stuurt niets naar derden — is first-party cookie).

```javascript
var params = new URLSearchParams(window.location.search);
var fbclid = params.get('fbclid');
if (fbclid) {
  var expires = new Date(Date.now() + 7 * 24 * 60 * 60 * 1000).toUTCString();
  document.cookie = '_fbclid=' + encodeURIComponent(fbclid)
    + '; expires=' + expires
    + '; path=/; SameSite=Lax; Secure';
}
```

- Cookie: `_fbclid`
- Levensduur: 7 dagen (overeenkomstig Meta's klikvenster)
- SameSite=Lax, Secure
- Mag vóór consent: het is een first-party cookie die niets naar derden stuurt

### E — Meta Pixel via GTM (alleen na consent)

**Trigger:** Consent Mode ad_storage = granted
**Events:**

| Event | Trigger |
|-------|---------|
| PageView | Elke pagina na consent |
| Lead | Formulier submit |
| video_start | Vimeo play |
| video_progress_25 | Vimeo 25% |
| video_progress_50 | Vimeo 50% |
| video_progress_75 | Vimeo 75% |
| video_complete | Vimeo 100% |
| calendly_cta_click | Klik op Calendly-knop |
| Schedule | Boeking voltooid |

Elk event krijgt een uniek `event_id` (UUID) voor deduplicatie met Fase 3.

### event_id Generator (GTM Custom JavaScript Variable)

```javascript
function() {
  return (typeof crypto !== 'undefined' && crypto.randomUUID)
    ? crypto.randomUUID()
    : Math.random().toString(36).substring(2) + Date.now().toString(36);
}
```

---

## Fase 2 — Attributie: Calendly → Zapier → Airtable → Meta CAPI

### F — Calendly URL Rewriter

GTM Custom HTML-tag, alleen op de videopagina. Leest `_fbclid` cookie en herschrijft Calendly-links.

```javascript
function getCookie(name) {
  var match = document.cookie.match(new RegExp('(^| )' + name + '=([^;]+)'));
  return match ? decodeURIComponent(match[2]) : null;
}

var fbclid = getCookie('_fbclid');
if (fbclid) {
  document.querySelectorAll('a[href*="calendly.com"]').forEach(function(link) {
    var url = new URL(link.href);
    url.searchParams.set('utm_content', 'fbclid_' + fbclid);
    url.searchParams.set('utm_source', 'meta');
    url.searchParams.set('utm_medium', 'paid_social');
    link.href = url.toString();
  });
}
```

**Resultaat:** `https://calendly.com/nextchapterbusiness/kennismaking?utm_content=fbclid_XXXX&utm_source=meta`

**Let op:** Check of Calendly inline embed is of redirect (OQ-9). Bij inline embed moet het script MutationObserver gebruiken om dynamisch geladen links te pakken.

### G — Zapier: Calendly → Airtable

Zapier-workflow in 3 stappen:

1. **Trigger:** Calendly — Invitee Created
2. **Formatter:** Text → Extract Pattern — verwijdert prefix `fbclid_` uit utm_content
3. **Action:** Airtable — Create Record

**Vereisten:**
- Calendly Standard of hoger (OQ-1)
- Zapier Starter of hoger voor multi-stap zaps (OQ-11)

**Veldkoppeling Zapier → Airtable:**

| Zapier veld | Airtable kolom |
|-------------|----------------|
| invitee.name | Naam |
| invitee.email | E-mail |
| invitee.questions_and_answers[phone] | Telefoon |
| event.start_time | Boekingstijd |
| Formatter output (fbclid) | fbclid |
| tracking.utm_source | utm_source |
| tracking.utm_medium | utm_medium |
| tracking.utm_campaign | utm_campaign |
| scheduled_event.uri (laatste deel) | Calendly UUID |
| Vaste waarde: "New Lead" | Status |

### H — Zapier: Airtable → Meta CAPI for CRM

Aparte zap. Verzendt bevestigde boekingen als CAPI-events naar Meta.

**Zapier App:** "Facebook Conversions (for Business Admins)"
**Let op:** Meta Offline Conversions API is in mei 2025 stopgezet. action_source: system_generated is de huidige standaardmethode.

**Payload:**
```json
{
  "event_name": "Lead",
  "event_time": "{unix_timestamp}",
  "action_source": "system_generated",
  "user_data": {
    "fbc": "fb.1.{ms_timestamp}.{fbclid}"
  }
}
```

**fbc-formaat:** `fb.1.{milliseconden_timestamp_klik}.{fbclid}`

**Vereist:** Meta CAPI Access Token vanuit Events Manager (OQ-5) — niet dezelfde als de CF2.0 native token die verwijderd moet worden.

---

## Fase 3 — Server-side: sGTM via TAGGRS + deduplicatie

### I — TAGGRS sGTM Container

Server-side GTM-container op subdomein `t.{domein}.com`.

**Vereist:**
- DNS CNAME-record: `t.{domein}.com` → TAGGRS endpoint (OQ-7)
- TAGGRS account

**Web GTM-configuratie:**
```javascript
gtag('config', '{MEASUREMENT_ID}', {
  'transport_url': 'https://t.{domein}.com',
  'first_party_collection': true
});
```

### J — Meta CAPI-tag in sGTM

De sGTM-container ontvangt events van de web GTM en stuurt ze server-side naar Meta.

**Voordelen:**
- Hogere datakwaliteit (IP-adres, User-Agent vanuit server)
- Werkt ook als browser de Pixel blokkeert
- Consent-gestuurd via GTM (niet mogelijk met native CF2.0 CAPI)

**Deduplicatie:**
- Browser-Pixel stuurt event met `event_id` (UUID)
- sGTM CAPI stuurt zelfde event met zelfde `event_id`
- Meta matcht op `event_name` + `event_id`
- Deduplicatievenster: 48 uur

### Verwijdering CF2.0 Native CAPI

Na Fase 3 live: de native CF2.0 CAPI is volledig vervangen. De Access Token moet al in Fase 1 verwijderd zijn (juridisch risico). In Fase 3 wordt de vervangende, consent-gestuurde server-side verbinding operationeel.

**Stappen verwijdering (meest urgent — vóór Fase 1):**
1. Open ClickFunnels 2.0 → Site & Blog → [sitenaam] → Settings
2. Ga naar Tracking Code
3. Scroll naar Facebook
4. Verwijder de Access Token uit het veld en sla op
5. Vraag screenshot voor en na (= antwoord op OQ-6)

---

## Vimeo Tracking (Fase 1 uitbreiding)

Voor Vimeo video milestones heb je de embed-code nodig (OQ-8). Het Vimeo Player API-script wordt geladen via GTM:

```javascript
var tag = document.createElement('script');
tag.src = 'https://player.vimeo.com/api/player.js';
document.head.appendChild(tag);
```

Vervolgens een listener per milestone:
```javascript
var iframe = document.querySelector('iframe[src*="vimeo"]');
var player = new Vimeo.Player(iframe);
var milestones = [25, 50, 75, 100];
var fired = {};

player.on('timeupdate', function(data) {
  var pct = Math.floor(data.percent * 100);
  milestones.forEach(function(m) {
    if (pct >= m && !fired[m]) {
      fired[m] = true;
      dataLayer.push({
        event: 'video_progress',
        video_percent: m,
        video_title: 'VSL'
      });
    }
  });
});

player.on('play', function() {
  dataLayer.push({ event: 'video_start', video_title: 'VSL' });
});
```
