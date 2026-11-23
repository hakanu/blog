---
published: true
layout: post
category: project
title: "Building hwprice.net: A Cross-Border European PC Hardware Price Tracker"
---

![GeForce RTX graphics card inside a PC build](/assets/img/hwprice-gpu-hero.jpg)
*Photo by [Matheus Bertelli](https://www.pexels.com/photo/close-up-of-geforce-rtx-graphics-card-in-pc-34552803/) on Pexels*

If you have ever tried buying a hard drive or a GPU in Europe, you already know the ritual: open Amazon.de, Amazon.nl, Amazon.fr, Amazon.it, Amazon.es, Alternate, Megekko, Coolblue, Proshop, Scan, then check Reddit and MyDealz, then peek at Marktplaats or Vinted to see if a used card makes more sense. Twenty browser tabs later, you still aren't sure if that "20% off" sticker is a real drop or just last month's normal price.

That annoyance is why I built **[hwprice.net](https://hwprice.net)**.

It started as a small script (`hdd_prices`) to track €/TB across European retailers while I was expanding my NAS. Over time it grew into a cross-border price tracker covering GPUs, CPUs, RAM, internal/external drives, mini PCs, and drive docks — all in one place, free to use, with no paywall.

## What hwprice.net does

The goal is simple: get you to **where to buy, at what price, and whether that price is actually good** as fast as possible.

- **Cross-border EU retail tracking (~15,000 active listings):** Compares the same hardware across Amazon EU storefronts and European shops (Alternate.nl/.de, Megekko, Coolblue, Proshop, Scan.co.uk, bol.com, and more) with a **"Ship to"** filter so you only see stores that actually deliver to your country. Filter by €/TB, chip, VRAM, capacity, or store.
- **Honest price history & `/hot-deals`:** Scraped price history exposes fake discounts and surfaces listings sitting at or near their 90-day lows on [hwprice.net/hot-deals](https://hwprice.net/hot-deals).
- **Community deals (`/deals`):** Aggregates hardware deals from Reddit (`r/BaPCSalesEurope`, UK/DE subs) and Pepper communities (MyDealz, Dealabs, HotUKDeals) alongside retail history at [hwprice.net/deals](https://hwprice.net/deals).
- **Used market (`/used`):** Tracks Marktplaats and Vinted listings for used GPUs, drives, and RAM — and keeps **sold listings** as a historical record with used medians so you can tell whether an asking price is fair.
- **Use-case tools tied to live prices:** Purpose-built guides (1080p–4K gaming, NAS, Jellyfin, homelab, local LLM rigs), GPU/CPU rankings, and a **Local AI finder** that maps open-weight LLMs to GPUs, Macs, and mini PCs using today's actual listings.
- **Watchlists & alerts:** Optional Google sign-in for price-drop email alerts and an opt-in weekly digest of notable drops and community deals.

![Close-up of server racks in a data center](/assets/img/hwprice-server-rack.jpg)
*Photo by [panumas nikhomkhai](https://www.pexels.com/photo/data-center-server-racks-with-active-equipment-37730212/) on Pexels*

## Under the hood: running it on a Raspberry Pi 5

One constraint I set early on was keeping the entire stack light, boring, and cheap to operate. The whole production site runs on a **Raspberry Pi 5** at home.

- **Backend & UI:** Python, Flask, and Gunicorn managed by PM2 (`hwprice_fe`). Pages are server-rendered with vanilla JS and compiled Tailwind CSS (no CDN runtime, no heavy SPA bundle) so pages stay fast and crawlable.
- **SQLite everywhere:** One SQLite database in WAL mode holds retail listings, price history, used marketplace records, and community deals. To keep the Pi 5 snappy under traffic, aggregate dashboard stats (facets, price buckets, brand averages) are precomputed after each scrape into a `category_stats_cache` table and served with `ETag` and `Cache-Control` headers.
- **Scheduled scraping pipeline:** Cronicle on my home server triggers foreground jobs on the Pi 5 for retail scrapes, community deals, used marketplaces, notifications, and weekly digests. Fetching runs through a small Playwright-based service (`browserful`) with a fast raw-HTML mode for server-rendered shops, a rendered fallback when needed, and daily raw-HTML caching so re-runs don't hammer retailers.
- **Local LLM enrichment:** Raw scraped listings are messy and thin for search engines. A background backfill job sends new products and community deals through my local LLM router to generate clean summaries and normalized specs — turning bare scrape rows into readable product pages.
- **SEO without crawl bloat:** Sitemaps are chunked (`/sitemap.xml`), thin/stale rows are excluded, and cross-locale Amazon duplicates for the same ASIN are consolidated with `rel=canonical` pointing to the primary locale and `noindex` on clones. After each scrape, updated URLs are pushed via IndexNow.

![Detailed close-up of a computer motherboard](/assets/img/hwprice-motherboard.jpg)
*Photo by [Pok Rie](https://www.pexels.com/photo/selective-focus-photo-of-dell-motherboard-1432669/) on Pexels*

## Try it out

If you are shopping for a drive, GPU, RAM kit, or mini PC anywhere in Europe, give **[hwprice.net](https://hwprice.net)** a spin — or jump straight into [Hot Deals](https://hwprice.net/hot-deals), [Community Deals](https://hwprice.net/deals), or the [Used Market](https://hwprice.net/used).

Some outbound retailer links are affiliate links (which is the only monetization; browsing, history, and alerts stay free). If there is a European shop or category you'd like to see added, feel free to ping me.
