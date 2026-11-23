---
published: true
layout: post
category: project
title: "Why I built hwprice.net: EU hardware prices and local LLM GPU reality checks"
---

![GeForce RTX graphics card inside a PC build](/assets/img/hwprice-gpu-hero.jpg)
*Photo by [Matheus Bertelli](https://www.pexels.com/photo/close-up-of-geforce-rtx-graphics-card-in-pc-34552803/) on Pexels*

TL;DR: I got tired of opening 15 European store tabs every time I needed a NAS drive or a GPU, and even more tired of digging through `r/LocalLLaMA` threads to figure out which GPU runs which open model. So I built **[hwprice.net](https://hwprice.net/)** for myself.

Every time I want to buy hardware in Europe, I hit the same wall. There isn't really a good, up-to-date cross-border price comparison site here. Sure, Tweakers is nice if you only care about the Netherlands, and Geizhals is decent for Germany, but in reality half the time a 12TB drive or a GPU is €50 cheaper on Amazon.de, Amazon.fr, Amazon.it, or a shop across the border that ships to you anyway.

So the usual routine was opening Amazon EU storefronts one by one, then Alternate, Megekko, Coolblue, Proshop, Scan, then checking Reddit, MyDealz, and Marktplaats to see what used prices look like. All of that just to do basic €/TB math and check if a "discount" is actually cheaper than last month.

It started as a tiny script (`hdd_prices`) to track hard drive prices while I was expanding my NAS. Then I started tinkering with local LLMs at home, and the project kind of snowballed from there.

## The local AI / local LLM itch nobody else scratches

If you run local AI models at home, you probably know how frustrating hardware shopping is right now. Normal PC hardware sites still rank GPUs almost purely by gaming FPS at 1440p. Almost nobody cares about the two questions I actually need answered every single time:

1. **Which local LLM can I actually run on this GPU (or Mac / mini PC)?**
2. **Which GPU do I need to run *this* specific model, and how much does it cost in Europe today?**

Normally that means digging through months-old `r/LocalLLaMA` threads, guessing quantization sizes, checking VRAM bandwidth on TechPowerUp, and then going back to 10 European store tabs to see if a 16GB or 24GB card is even reasonably priced this week.

So I baked that straight into the site, tied to live EU prices:

- **[Local AI Finder](https://hwprice.net/local-ai)** & **[Local AI Models](https://hwprice.net/local-ai/models)**: pick a GPU, Mac, or mini PC to see which open models fit in its VRAM/unified memory, or start from a model you want to run and see which GPUs/systems can handle it with today's European prices right next to them.
- **[European GPU price & VRAM rankings](https://hwprice.net/gpus)**: sorted and filterable by VRAM, chip, and actual street price across EU stores instead of MSRP fantasies.
- **[Local LLM GPU guide](https://hwprice.net/guides/local-llm-gpu)**: breaks down the practical sweet spots for running local LLMs on European GPU pricing (and there's also an [EU GPU price index](https://hwprice.net/guides/eu-gpu-price-index) to see where prices are drifting).

![Close-up of server racks in a data center](/assets/img/hwprice-server-rack.jpg)
*Photo by [panumas nikhomkhai](https://www.pexels.com/photo/data-center-server-racks-with-active-equipment-37730212/) on Pexels*

## The rest of what I threw in there

Beyond local AI stuff, I kept adding the views I use whenever I'm buying parts for my homelab:

- **[EU PC hardware & NAS drive price tracker](https://hwprice.net/)**: drives, GPUs, CPUs, RAM, mini PCs, and docks across Amazon EU storefronts and European shops, with a "Ship to" filter so you don't waste clicks on stores that don't ship to your country.
- **[Community deals](https://hwprice.net/deals) & [second-hand hardware](https://hwprice.net/used)**: aggregates deals from Reddit (`r/BaPCSalesEurope`, etc.), MyDealz, Dealabs, and HotUKDeals, plus used listings from Marktplaats and Vinted. I keep **sold** used listings as a record too, so you can see what a used card actually went for instead of trusting wishful asking prices.

## How it's hosted (yep, on a Raspberry Pi 5)

Since this is a side project I built out of necessity, I didn't want a cloud server bill hanging over it. The whole thing runs on a **Raspberry Pi 5** sitting in my homelab.

- **Stack:** Python, Flask, Gunicorn under PM2, vanilla JS, and compiled Tailwind CSS. Server-rendered HTML keeps it light on the Pi and easy to crawl.
- **SQLite:** Everything (retail listings, price history, community deals, used listings) lives in one SQLite DB in WAL mode. After each scrape, stats and facets get precomputed into a cache table so requests stay fast.
- **Scraping:** Cronicle on my home server triggers jobs on the Pi. Fetching goes through a small Playwright helper (`browserful`) with a fast raw-HTML mode and daily HTML caching so I'm not hammering stores unnecessarily.
- **Local LLM enrichment:** Raw retailer titles are a mess, so a background job sends new listings through my own local LLM router at home to extract clean specs and short summaries. (Eating my own dog food there.)

![Detailed close-up of a computer motherboard](/assets/img/hwprice-motherboard.jpg)
*Photo by [Pok Rie](https://www.pexels.com/photo/selective-focus-photo-of-dell-motherboard-1432669/) on Pexels*

It's still a work in progress and scraping European stores is always a bit of cat-and-mouse, so freshness varies by shop. Some outbound links are affiliate links just to help cover electricity/time, nothing is paywalled.

If you're in Europe hunting for NAS drives, used GPUs, or trying to figure out what local LLM setup makes sense without spending an evening on `r/LocalLLaMA`, give **[hwprice.net](https://hwprice.net/)** a look and let me know what's missing.
