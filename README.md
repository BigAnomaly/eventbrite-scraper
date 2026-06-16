[Eventbrite Scraper](https://apify.com/santamaria-automations/eventbrite-scraper?fpr=data)

Scrape event data from Eventbrite.com, the world's largest event platform with millions of events in 180+ countries.

## What data can you extract?

- **Event details**: title, description, start/end dates, timezone
- **Venue info**: name, full address, city, country, GPS coordinates
- **Pricing**: ticket price, currency, free/paid status
- **Organizer**: name and profile URL
- **Categories & tags**: event category, subcategory, format, and organizer tags
- **Media**: event image URL

## Use with AI Agents (MCP)

Connect this actor to any MCP-compatible AI client — Claude Desktop, Claude.ai, Cursor, VS Code, LangChain, LlamaIndex, or custom agents.

**Apify MCP server URL:**

```
https://mcp.apify.com?tools=santamaria-automations/eventbrite-scraper
```

**Example prompt once connected:**

> "Use `eventbrite-scraper` to scrape company data from eventbrite. Return results as a table."

Clients that support dynamic tool discovery (Claude.ai, VS Code) will receive the full input schema automatically via `add-actor`.

## How to use

### Option 1: Search URLs

Paste any Eventbrite search URL directly:

```
{
  "searchUrls": [
    "https://www.eventbrite.com/d/germany/tech/",
    "https://www.eventbrite.com/d/ca--san-francisco/conferences/"
  ],
  "maxResults": 100
}
```

### Option 2: Search query + location

```
{
  "searchQuery": "tech",
  "location": "germany",
  "maxResults": 50
}
```

### Location format

Eventbrite uses URL slugs for locations:

- Countries: `germany`, `united-states`, `france`
- Regions: `united-states--new-york`, `germany--berlin`
- Cities: `ca--san-francisco`, `united-kingdom--london`
- Online: `online`

## Input parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `searchUrls` | string[] | - | Eventbrite search page URLs |
| `searchQuery` | string | - | Search keyword |
| `location` | string | `germany` | Location slug for URL building |
| `maxResults` | integer | 100 | Maximum events to scrape (1-5000) |
| `proxyConfiguration` | object | RESIDENTIAL proxy | Proxy settings (residential required) |

## Output example

```
{
  "id": "1982303023706",
  "title": "Women in Tech Connect Berlin 2026",
  "description": "This event is part of the Women in Tech Global Conference...",
  "start_date": "2026-05-12T09:00:00+02:00",
  "end_date": "2026-05-12T18:00:00+02:00",
  "timezone": "Europe/Berlin",
  "url": "https://www.eventbrite.com/e/women-in-tech-connect-berlin-tickets-1980168035900",
  "image_url": "https://img.evbuc.com/...",
  "is_free": false,
  "is_online": false,
  "price": "49.00",
  "currency": "EUR",
  "venue_name": "Berlin Conference Center",
  "venue_address": "Alexanderplatz 1, 10178 Berlin",
  "venue_city": "Berlin",
  "venue_country": "DE",
  "latitude": 52.5200,
  "longitude": 13.4050,
  "organizer_name": "Women in Tech Network",
  "organizer_url": "https://www.eventbrite.com/o/women-in-tech-12345",
  "category": "Science & Technology",
  "tags": ["High Tech", "Conference", "Networking"],
  "attendee_count": null,
  "source_url": "https://www.eventbrite.com/d/germany/tech/",
  "source_platform": "eventbrite.com",
  "scraped_at": "2026-03-31T12:00:00Z"
}
```

## Performance

- ~128MB memory (Go binary with TLS fingerprinting)
- ~20 events per search page
- Fetches detail pages for price and organizer data
- RESIDENTIAL proxy required (Eventbrite blocks datacenter IPs)

## Pricing

Pay per result: $0.003 per event extracted.

## Related Actors

**Related Scrapers**

- [Google News Scraper — News articles](https://apify.com/santamaria-automations/google-news-scraper)
- [YouTube Scraper — Video & channel data](https://apify.com/santamaria-automations/youtube-scraper)
- [Similarweb Scraper — Website analytics](https://apify.com/santamaria-automations/similarweb-scraper)

**European Classifieds**

- [Kleinanzeigen.de Scraper — Germany](https://apify.com/santamaria-automations/kleinanzeigen-de-scraper)
- [Willhaben.at Scraper — Austria](https://apify.com/santamaria-automations/willhaben-at-scraper)
- [Tutti.ch Scraper — Switzerland](https://apify.com/santamaria-automations/tutti-ch-scraper)
- [Marktplaats.nl Scraper — Netherlands](https://apify.com/santamaria-automations/marktplaats-nl-scraper)

**Enrich your data**

- [Website Email & Phone Scraper](https://apify.com/santamaria-automations/website-email-scraper)
- [Google Maps Scraper](https://apify.com/santamaria-automations/google-maps-scraper)
- [Website Contact Extractor](https://apify.com/santamaria-automations/website-contact-extractor)

## Issues & Feature Requests

If something is not working or you're missing a feature or data field, please [open an issue](https://console.apify.com/actors/bn1zqW7IDOoj5evZl/issues) and we'll look into it.