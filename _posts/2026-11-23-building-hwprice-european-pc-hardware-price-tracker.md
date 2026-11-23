---
published: true
layout: post
category: project
title: "Why I built hwprice.net: scratching my own itch for EU hardware prices"
---

![GeForce RTX graphics card inside a PC build](/assets/img/hwprice-gpu-hero.jpg)
*Photo by [Matheus Bertelli](https://www.pexels.com/photo/close-up-of-geforce-rtx-graphics-card-in-pc-34552803/) on Pexels*

Every time I needed to buy a hard drive for my NAS or hunt for a GPU in Europe, I ran into the same annoying problem: there isn't really a good, up-to-date, cross-border price comparison site for EU hardware.

Sure, there are country-specific sites (Tweakers in the Netherlands, Geizhals in Germany, etc.), and they're fine if you only shop locally. But in practice, half the time a drive or a GPU is €40–€80 cheaper on Amazon.de, Amazon.fr, Amazon.it, or a shop one border over that ships to you anyway. So I'd end up with 15 tabs open — Amazon EU storefronts, Alternate, Megekko, Coolblue, Proshop, Scan, Reddit, MyDealz, Marktplaats — doing mental math on €/TB and trying to figure out if a "deal" was actually cheaper than last month.

Eventually I got tired of doing this manually and wrote a small scraper (`hdd_prices`) just to track €/TB on NAS drives for myself. Like most side projects that get out of hand, it snowballed into a full site: **[hwprice.net](https://hwprice.net/)**.

## What it turned into

I mostly kept adding the pages I personally wished existed whenever I was buying parts for my homelab or local AI experiments:

- **[EU PC hardware & NAS drive price tracker](https://hwprice.net/)** — compares drives, GPUs, CPUs, RAM, mini PCs, and docks across Amazon EU stores and European retailers, with a "Ship to" filter and €/TB sorting so I don't waste time on stores that won't deliver to me.
- **[European GPU price & VRAM rankings](https://hwprice.net/gpus)** — since I've been tinkering with local LLMs, VRAM per euro matters to me a lot more than marketing tiers. Having GPU prices, VRAM, and price history in one table saved me a ton of spreadsheet work.
- **[Local LLM GPU guide](https://hwprice.net/guides/local-llm-gpu)** — ties those live European GPU prices directly to which open-weight models actually fit and run well on each card (also have an [EU GPU price index](https://hwprice.net/guides/eu-gpu-price-index) tracking where prices are drifting).
- **[Community deals](https://hwprice.net/deals) & [second-hand hardware](https://hwprice.net/used)** — pulls in deals from Reddit (`r/BaPCSalesEurope`, etc.), MyDealz, Dealabs, and HotUKDeals, plus used listings from Marktplaats and Vinted. I keep sold used listings around too so I can see what people *actually* paid instead of just guessing from asking prices.

![Close-up of server racks in a data center](/assets/img/hwprice-server-rack.jpg)
*Photo by [panumas nikhomkhai](https://www.pexels.com/photo/data-center-server-racks-with-active-equipment-37730212/) on Pexels*

## How it runs (all on a Raspberry Pi 5)

Since this is a personal project and I didn't want a cloud bill for it, the whole thing runs at home on a **Raspberry Pi 5**.

- **Stack:** Python, Flask, and Gunicorn under PM2, with vanilla JS and compiled Tailwind CSS. Server-rendered HTML keeps it lightweight for the Pi and easy for search engines to crawl.
- **One SQLite DB:** Everything — retail listings, price history, community deals, and used listings — lives in a single SQLite database in WAL mode. After each scrape, a script precomputes the category facets and stats into a cache table so page loads stay fast even on a Pi.
- **Scraping:** Scheduled via Cronicle on my home server (`nashaku`), running jobs on `pi5`. Fetching goes through a small Playwright helper (`browserful`) with a raw-HTML fast path and daily raw-HTML caching so I'm not re-fetching the same pages over and over.
- **Local LLM backfill:** Raw store titles are messy, so a background job runs new listings through my local LLM router to clean up specs and write short summaries.

![Detailed close-up of a computer motherboard](/assets/img/hwprice-motherboard.jpg)
*Photo by [Pok Rie](https://www.pexels.com/photo/selective-focus-photo-of-dell-motherboard-1432669/) on Pexels*

It's still very much a work in progress — coverage and freshness depend on how cooperative each retailer's HTML is on any given day — and some outbound store links are affiliate links just to help offset the time/electricity. Mostly I just wanted a tool I'd actually use myself whenever I'm buying another 12TB drive or eyeing a used GPU.

If you're in Europe and do the same 15-tab dance when buying hardware, feel free to poke around **[hwprice.net](https://hwprice.net/)** and let me know if there's an EU shop worth adding.
