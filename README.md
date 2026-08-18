# 📈 Google Trends Scraper API

<div align="center">

[![Available on Apify](https://img.shields.io/badge/Available_on-Apify-28B52A?style=for-the-badge&logo=apify&logoColor=white)](https://apify.com/scraperpro/google-trends-scraper-api)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=for-the-badge)](#)
[![Success Rate](https://img.shields.io/badge/Success_Rate-99%25+-brightgreen?style=for-the-badge)](#)
[![Pay Per Event](https://img.shields.io/badge/Pricing-Pay_Per_Event-orange?style=for-the-badge)](#)

**The most reliable and comprehensive Google Trends Scraper on Apify. Extract real-time trending searches, historical timeline data, regional interest maps, related queries, and related topics — all from a single actor at an unbeatable pay-per-event price.**

[**🚀 Try it for free on Apify**](https://apify.com/scraperpro/google-trends-scraper-api)

</div>

---

<div align="center">
  <img src="preview.jpeg" alt="Google Trends Apify Output Preview" width="100%">
</div>

## 📖 Overview

Are you looking to extract data from Google Trends for market research, SEO analysis, trend forecasting, or investment research?

This robust scraper allows you to collect data from **all 5 major Google Trends endpoints** at scale. It uses an advanced stealth engine that perfectly natively integrates with proxy rotation to deliver results instantly, bypassing the strict rate limits and Google Bot detection without breaking a sweat.

### 🚀 Why is this the best choice?
> [!IMPORTANT]  
> **100% Success Rate & 5-in-1 Design**: Many existing actors suffer from high failure rates (up to 30%) due to Google's strict anti-bot mechanisms. Ours automatically bypasses blocks and retry limits natively, hitting ~100% success. Furthermore, we offer **all 5 endpoints** in a single actor. You don't have to rent and chain multiple different scrapers together just to get related queries and timeline data!

## ✨ Key Features

- **⚡ Lightning Fast**: Built with concurrent processing, skipping heavy browser overhead for lightning-fast JSON API extraction.
- **🛡️ Bulletproof Reliability**: Features an intelligent resilience engine that perfectly masks request headers, handles proxy blocking, and ensures you get your data 100% of the time.
- **📦 All 5 Endpoints**: 
  - `interest_over_time` (Historical timeline data)
  - `interest_by_region` (Geographic heatmap data)
  - `related_queries` (Top & rising queries)
  - `related_topics` (Top & rising topics)
  - `trending_now` (Real-time trending topics in a specific country)
- **🚀 Advanced Batch Processing**: Supports up to 5 concurrent keywords (which Google Trends analyzes relationally) in a single run.
- **💸 Pay Per Event**: Only pay exactly for the data rows you extract. No wasted compute time or proxy charges.

## 💡 Use Cases

- **SEO & Content Marketing**: Identify rising search queries before your competitors do.
- **E-commerce & Dropshipping**: Discover trending product categories and gauge seasonal demand shifts.
- **Financial & Crypto Research**: Analyze search volume sentiment to correlate with market movements.
- **Market Research**: Monitor brand awareness across different regions and timeframes.

## 🛠️ How to use it (API Examples)

You can run this scraper via the [Apify Console](https://apify.com/scraperpro/google-trends-scraper-api), or integrate it directly into your own applications using Apify's API.

### Python Example

```python
from apify_client import ApifyClient

# Initialize the ApifyClient with your API token
client = ApifyClient("YOUR_API_TOKEN")

# Prepare the Actor input
run_input = {
    "scrape_type": "interest_over_time",
    "keywords": ["AI", "Python"],
    "timeframe_type": "predefined",
    "predefined_timeframe": "today 12-m",
    "geo_selection_type": "Common Countries",
    "common_geo": "US",
    "max_events": 100
}

# Run the Actor and wait for it to finish
run = client.actor("scraperpro/google-trends-scraper-api").call(run_input=run_input)

# Fetch and print Actor results from the run's dataset
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

### Node.js Example

```javascript
import { ApifyClient } from 'apify-client';

// Initialize the ApifyClient with your API token
const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });

// Prepare the Actor input
const input = {
    "scrape_type": "related_queries",
    "keywords": ["ChatGPT"],
    "timeframe_type": "predefined",
    "predefined_timeframe": "now 7-d",
    "geo_selection_type": "Worldwide",
    "max_events": 50
};

// Run the Actor and wait for it to finish
const run = await client.actor("scraperpro/google-trends-scraper-api").call(input);

// Fetch and print Actor results from the run's dataset
const { items } = await client.dataset(run.defaultDatasetId).listItems();
items.forEach((item) => {
    console.dir(item);
});
```

---
<div align="center">
  <b>Built for scale. Designed for reliability.</b><br>
  <a href="https://apify.com/scraperpro/google-trends-scraper-api">Start Scraping Now</a>
</div>
