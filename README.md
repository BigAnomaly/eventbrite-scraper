[Eventbrite Scraper](https://apify.com/newpo/eventbrite-scraper?fpr=data)

# 🎟️ Eventbrite Events Scraper (Beginner-Friendly + Backward Compatible)

Scrape Eventbrite event data from listing/search pages in minutes.

## Input modes

### 1) Paste URL mode (original + backward compatible)

Paste Eventbrite listing URLs directly.

### 2) Guided mode (human-friendly)

Use simple inputs like:

- **Location:** `Miami Beach, FL` or `Dallas, TX`
- **When:** Today / This week / This weekend / This month
- Optional **Keyword**

The actor converts your location into Eventbrite format automatically.

## Notes

- Existing users can continue using `startUrls` exactly as before.
- If `startUrls` is provided, it takes priority.

## Sample output

```
[
  {
    "id": "1980427365562",
    "crawled_at": "2026-02-23T16:09:46.987Z",
    "url": "https://www.eventbrite.com/e/icon-the-show-birthday-bash-2026-tickets-1980427365562",
    "@context": "https://schema.org",
    "@type": "SocialEvent",
    "name": "ICON THE SHOW BIRTHDAY BASH 2026",
    "description": "Get ready to party hard at ICON THE SHOW BIRTHDAY BASH 2026—big vibes, live fun, and epic memories!",
    "image": "https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F1174685817%2F213302679580%2F1%2Foriginal.20260113-004538?w=480&auto=format%2Ccompress&q=75&sharp=10&s=5403a7c78b93af4fec07ff1878d4d23e",
    "eventStatus": "https://schema.org/EventScheduled",
    "location": {
      "@type": "Place",
      "name": "Rose Room",
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Dallas",
        "addressRegion": "TX",
        "addressCountry": "US",
        "streetAddress": "3911 Cedar Springs Road, Dallas, TX 75219"
      }
    },
    "organizer": {
      "@type": "Organization",
      "name": "Kohl Faulkner",
      "url": "https://www.eventbrite.com/o/kohl-faulkner-52460872393"
    },
    "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
    "startDate": "2026-03-01T18:00:00-06:00",
    "endDate": "2026-03-01T20:30:00-06:00",
    "offers": [
      {
        "@type": "AggregateOffer",
        "lowPrice": "30.87",
        "highPrice": "42.42",
        "url": "https://www.eventbrite.com/e/icon-the-show-birthday-bash-2026-tickets-1980427365562",
        "availability": "InStock",
        "availabilityStarts": "2026-01-12T06:00:00Z",
        "availabilityEnds": "2026-03-01T12:00:00Z",
        "validFrom": "2026-01-12T06:00:00Z",
        "priceCurrency": "USD"
      }
    ]
  },
  {
    "id": "1980051482285",
    "crawled_at": "2026-02-23T16:09:48.385Z",
    "url": "https://www.eventbrite.com/e/lace-mascara-and-mocktails-mixer-tickets-1980051482285",
    "@context": "https://schema.org",
    "@type": "SocialEvent",
    "name": "LACE Mascara and Mocktails Mixer",
    "description": "Ladies Alive Connect Events presents the \"Mascara and Mocktails Mixer\" - come connect and meet ladies to add to your girlfriend tribe.",
    "image": "https://img.evbuc.com/https%3A%2F%2Fcdn.evbuc.com%2Fimages%2F1175179863%2F759546082533%2F1%2Foriginal.20260118-175059?crop=focalpoint&fit=crop&w=480&auto=format%2Ccompress&q=75&sharp=10&fp-x=0.871&fp-y=0.299&s=41aab90e1360f02f8feff96ccbd3ac72",
    "eventStatus": "https://schema.org/EventScheduled",
    "location": {
      "@type": "Place",
      "name": "New Covenant House",
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Farmers Branch",
        "addressRegion": "TX",
        "addressCountry": "US",
        "streetAddress": "12921 Senlac Drive, Farmers Branch, TX 75234"
      }
    },
    "organizer": {
      "@type": "Organization",
      "name": "New Covenant House",
      "url": "https://www.eventbrite.com/o/new-covenant-house-39749984683"
    },
    "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
    "startDate": "2026-02-27T19:00:00-06:00",
    "offers": [
      {
        "@type": "AggregateOffer",
        "lowPrice": "0.0",
        "highPrice": "23.18",
        "url": "https://www.eventbrite.com/e/lace-mascara-and-mocktails-mixer-tickets-1980051482285",
        "availability": "InStock",
        "availabilityStarts": "2026-01-07T06:00:00Z",
        "availabilityEnds": "2026-02-28T01:00:00Z",
        "validFrom": "2026-01-07T06:00:00Z",
        "priceCurrency": "USD"
      }
    ]
  }
]
```