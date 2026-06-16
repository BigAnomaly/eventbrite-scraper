[Eventbrite Scraper](https://apify.com/fortuitous_pirate/eventbrite-scraper?fpr=data)

# Eventbrite Scraper

## Overview

Scrape events from Eventbrite including event name, description, date, time, timezone, location, venue, price, organizer, category, and images. Supports filters (Location, Category, Date Range).

## Features

- Search by keywords to find specific results
- Filter results by category or type
- Export data in JSON, CSV, or Excel formats
- Captures pricing information
- Includes location and address data
- Captures images and media URLs

## Use Cases

- **Track** - Track event listings and ticket availability
- **Build** - Build event databases for aggregation platforms
- **Monitor** - Monitor event pricing and scheduling trends
- **Aggregate** - Aggregate event data for planning and discovery

## Input Parameters

| Parameter | Type | Description | Default |
| --- | --- | --- | --- |
| `location` | string **(required)** | City or address to search for events (e.g., 'austin', 'new-york', 'los-angeles') | `austin` |
| `category` | string | Event category to filter by | `` |
| `dateRange` | string | Filter events by date range | `` |
| `maxItems` | integer | Maximum number of events to scrape | `50` |
| `proxyConfiguration` | object | Proxy settings for bypassing rate limits | `{...}` |

## Output Example

Each result contains structured data like this:

```
{
  "title": "Sample Events Result",
  "date": "2025-01-15",
  "location": "San Francisco, CA",
  "venue": "Convention Center",
  "price": 29.99,
  "category": "Standard",
  "url": "https://example.com/item/12345"
}
```

## Pricing

This actor uses pay-per-result pricing:

- **$0.001** per result
- **$1.00** per 1,000 results

No monthly fees. You only pay for what you scrape. [Apify Free plan](https://apify.com/pricing) includes $5/month in platform credits.

## How to Run

### Apify Console

1. Go to the [Eventbrite Scraper](https://apify.com/fortuitous_pirate/eventbrite-scraper) actor page
2. Configure your input parameters
3. Click **Start** and wait for the results
4. Download data in JSON, CSV, or Excel format

### API

```
curl -X POST "https://api.apify.com/v2/acts/fortuitous_pirate~eventbrite-scraper/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"maxItems": 10}'
```

### Python SDK

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("fortuitous_pirate/eventbrite-scraper").call(
    run_input={"maxItems": 10}
)

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Integration

Connect Eventbrite Scraper with your existing tools and workflows:

- **API access** - Programmatic access via [Apify API](https://docs.apify.com/api/v2)
- **Webhooks** - Get notified when scraping completes
- **Scheduling** - Set up recurring runs on any schedule
- **Zapier / Make** - Connect with 5,000+ apps via [Apify integrations](https://apify.com/integrations)
- **Python / Node.js SDKs** - Native client libraries for easy integration