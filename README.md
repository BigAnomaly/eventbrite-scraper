[Eventbrite Scraper](https://apify.com/lulzasaur/eventbrite-scraper?fpr=data)

Scrape events from [Eventbrite](https://www.eventbrite.com) — the world's largest event discovery platform. Search by keyword, location, date range, category, and price. Extract event details, venues, ticket prices, organizer info, and more.

## Features

- **Search events** by keyword, city, date range, category, and price filter
- **20+ fields** per event: title, date, time, venue, address, city, price, organizer, image, category, and more
- **Detail page scraping** (optional) — visit each event page for full descriptions, ticket price ranges, organizer details, and tags
- **Pagination** — automatically follows all pages of results
- **Proxy support** — built-in residential proxy support for large-scale runs
- **700+ cities** searchable via Eventbrite's location slugs

## Output Fields

### Search Mode (default)

| Field | Description |
| --- | --- |
| `eventId` | Eventbrite event ID |
| `title` | Event title |
| `date` | Start date (YYYY-MM-DD) |
| `time` | Start time (HH:MM, 24h) |
| `endDate` | End date |
| `endTime` | End time |
| `timezone` | Timezone (e.g., America/Los_Angeles) |
| `venue` | Venue name |
| `address` | Street address |
| `city` | City name |
| `state` | State/region |
| `country` | Country code |
| `postalCode` | Postal/ZIP code |
| `latitude` | GPS latitude |
| `longitude` | GPS longitude |
| `imageUrl` | Event image URL |
| `eventUrl` | Link to event page |
| `category` | Event category (Music, Food & Drink, etc.) |
| `description` | Short description/summary |
| `isOnline` | Whether it's an online event |
| `ticketsUrl` | Direct link to ticket purchase |
| `searchQuery` | The search query used |
| `scrapedAt` | ISO timestamp of scrape |

### Detail Mode (with `scrapeDetails: true`)

All fields above, plus:

| Field | Description |
| --- | --- |
| `price` | Formatted price string (e.g., "Free", "$25", "$50 - $200") |
| `lowPrice` | Lowest ticket price (number) |
| `highPrice` | Highest ticket price (number) |
| `priceCurrency` | Currency code (e.g., USD) |
| `isFree` | Whether the event is free |
| `availability` | Ticket availability (InStock, SoldOut, etc.) |
| `organizer` | Organizer name |
| `organizerUrl` | Organizer profile URL |
| `organizerDescription` | Organizer bio |
| `fullDescription` | Full event description text |
| `performers` | Array of performer names |
| `tags` | Array of event tags |
| `eventStatus` | Event status (EventScheduled, EventCancelled, etc.) |

## Example Output

### Search Result

```
{
  "eventId": "1969285167949",
  "title": "AI Dev 26 x SF — The AI Developer Conference",
  "date": "2026-04-28",
  "time": "07:00",
  "endDate": "2026-04-29",
  "endTime": "18:00",
  "timezone": "America/Los_Angeles",
  "venue": "Pier 48 Shed B",
  "address": "Pier 48",
  "city": "San Francisco",
  "state": "CA",
  "country": "US",
  "postalCode": "94158",
  "latitude": 37.7749,
  "longitude": -122.4194,
  "imageUrl": "https://img.evbuc.com/...",
  "eventUrl": "https://www.eventbrite.com/e/ai-dev-26-x-sf-...",
  "category": "Science & Tech",
  "description": "Join us for two days of coding, learning, and connecting...",
  "isOnline": false,
  "scrapedAt": "2026-04-23T12:00:00.000Z"
}
```

### Detail Result (with scrapeDetails)

```
{
  "eventId": "1969285167949",
  "title": "AI Dev 26 x SF — The AI Developer Conference",
  "date": "2026-04-28",
  "time": "07:00",
  "venue": "Pier 48 Shed B",
  "city": "San Francisco",
  "state": "CA",
  "price": "$534.31 - $1387.97",
  "lowPrice": 534.31,
  "highPrice": 1387.97,
  "priceCurrency": "USD",
  "isFree": false,
  "availability": "InStock",
  "organizer": "DeepLearning.AI",
  "organizerUrl": "https://www.eventbrite.com/o/deeplearningai-19822694300",
  "fullDescription": "Join us for two days of coding, learning, and connecting to build AI applications...",
  "tags": ["Science & Tech", "Conference"],
  "scrapedAt": "2026-04-23T12:00:00.000Z"
}
```

## Input Examples

### Search events by keyword

```
{
  "query": "jazz",
  "location": "ca--san-francisco",
  "limit": 50
}
```

### Free events this weekend

```
{
  "location": "ny--new-york",
  "dateRange": "this-weekend",
  "priceRange": "free",
  "limit": 100
}
```

### Music events with full details

```
{
  "location": "il--chicago",
  "category": "music",
  "scrapeDetails": true,
  "limit": 30
}
```

### Business events this month

```
{
  "query": "conference",
  "location": "wa--seattle",
  "category": "business",
  "dateRange": "this-month",
  "limit": 50
}
```

## Location Slugs

Common location slugs for the `location` input:

| Location | Slug |
| --- | --- |
| San Francisco | `ca--san-francisco` |
| New York | `ny--new-york` |
| Los Angeles | `ca--los-angeles` |
| Chicago | `il--chicago` |
| Austin | `tx--austin` |
| Seattle | `wa--seattle` |
| Denver | `co--denver` |
| Boston | `ma--boston` |
| Miami | `fl--miami` |
| Portland | `or--portland` |
| Online Events | `online--online` |

Format: `{state-abbreviation}--{city-name}` (lowercase, dashes for spaces)

## Use Cases

- **Event discovery** — Find events in any city by keyword, category, or date
- **Market research** — Analyze event pricing, categories, and trends
- **Competitor analysis** — Track events by specific organizers or categories
- **Venue intelligence** — Map events to venues and locations
- **Price monitoring** — Track ticket pricing across events
- **Content curation** — Build event feeds for newsletters or apps
- **Community management** — Find relevant events for your community

## Date Filters

| Filter | Description |
| --- | --- |
| `today` | Events happening today |
| `tomorrow` | Events happening tomorrow |
| `this-weekend` | Events this weekend |
| `this-week` | Events this week |
| `next-week` | Events next week |
| `this-month` | Events this month |
| `next-month` | Events next month |

## Category Filters

| Category | Slug |
| --- | --- |
| Music | `music` |
| Food & Drink | `food-and-drink` |
| Business | `business` |
| Performing & Visual Arts | `performing-visual-arts` |
| Health | `health` |
| Science & Tech | `science-and-tech` |
| Sports & Fitness | `sports-and-fitness` |
| Travel & Outdoor | `travel-and-outdoor` |
| Charity & Causes | `charity-and-causes` |
| Community | `community` |
| Film & Media | `film-and-media` |
| Fashion | `fashion` |
| Hobbies | `hobbies` |
| Home & Lifestyle | `home-and-lifestyle` |
| Family & Education | `family-and-education` |

---

## Run on Apify

This scraper runs on the [Apify platform](https://apify.com/?fpr=lulzasaur) — a full-stack web scraping and automation cloud. Sign up for a free account to get started with a 30-day trial of all features.

[Try Apify free ->](https://apify.com/?fpr=lulzasaur)