---
layout: page
title: About
author: Hakan Uysal
permalink: /about/
published: true
---

I'm Hakan Uysal. I like building weekend projects, homelab tools, and small web/mobile apps — most of my active work lives under **[Yaz Labs](https://yazlabs.com)**.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Story of my life <a href="https://t.co/QdsYyjFG8m">pic.twitter.com/QdsYyjFG8m</a></p>&mdash; Hakan Uysal (@hakanu_) <a href="https://twitter.com/hakanu_/status/1062646164879826944?ref_src=twsrc%5Etfw">November 14, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Live Projects

Active web and mobile products I build and run (also showcased on [yazlabs.com](https://yazlabs.com), [Google Play](https://play.google.com/store/apps/developer?id=Yaz+Labs), and the [App Store](https://apps.apple.com/developer/hakan-uysal/id6829677084)).

<div class="project-grid">
{%- assign products = site.data.projects.projects | where: "kind", "product" -%}
{%- for p in products -%}
  <article class="project-item">
    <a class="project-thumb-link" href="{{ p.url }}" target="_blank" rel="noopener">
      <img class="project-thumb" src="{{ p.thumbnail | relative_url }}" alt="{{ p.title | escape }} — {{ p.tagline | escape }}" loading="lazy">
    </a>
    <div class="project-body">
      <h3 class="project-name">
        <a href="{{ p.url }}" target="_blank" rel="noopener">{{ p.title | escape }}</a>
      </h3>
      <p class="project-tagline">{{ p.tagline | escape }}</p>
      <p class="project-desc">{{ p.description | escape }}</p>
      <div class="project-links">
        <a href="{{ p.url }}" target="_blank" rel="noopener">{{ p.url | remove: "https://" | remove: "http://" | split: "/" | first }}</a>
        {%- if p.apps.android and p.apps.android != p.url -%}
          <span class="meta-sep" aria-hidden="true">·</span>
          <a href="{{ p.apps.android }}" target="_blank" rel="noopener">{{ p.apps.android_label | default: "Android" }}</a>
        {%- endif -%}
        {%- if p.apps.ios -%}
          <span class="meta-sep" aria-hidden="true">·</span>
          <a href="{{ p.apps.ios }}" target="_blank" rel="noopener">iOS</a>
        {%- endif -%}
      </div>
    </div>
  </article>
{%- endfor -%}
</div>

## Client Work

Websites and custom tools built for clients through [Yaz Labs](https://yazlabs.com).

<div class="project-grid">
{%- assign clients = site.data.projects.projects | where: "kind", "client" -%}
{%- for p in clients -%}
  <article class="project-item">
    <a class="project-thumb-link" href="{{ p.url }}" target="_blank" rel="noopener">
      <img class="project-thumb" src="{{ p.thumbnail | relative_url }}" alt="{{ p.title | escape }} — {{ p.tagline | escape }}" loading="lazy">
    </a>
    <div class="project-body">
      <h3 class="project-name">
        <a href="{{ p.url }}" target="_blank" rel="noopener">{{ p.title | escape }}</a>
      </h3>
      <p class="project-tagline">{{ p.tagline | escape }}</p>
      <p class="project-desc">{{ p.description | escape }}</p>
      <div class="project-links">
        <a href="{{ p.url }}" target="_blank" rel="noopener">{{ p.url | remove: "https://" | remove: "http://" | split: "/" | first }}</a>
      </div>
    </div>
  </article>
{%- endfor -%}
</div>

## Open Source, Tools & Channels

- **[Pervane](https://github.com/hakanu/pervane)** — Open-source plain-text / Markdown file-based note-taking web app.
- **[Bank Statement Analyzer](https://bank.hakanu.net)** — Upload CSV or PDF bank statements and let AI categorize spendings into charts.
- **[Irem HackerTyper](https://irem.hakanu.net)** — HackerTyper for Turkish developers with "Irem - Hayalet Sevgilim" lyrics.
- **[Eksistats](https://paylas.io/r/eksistats)** — NLP experiments over Ekşi Sözlük.
- **[Güldüm.net on Instagram](https://instagram.com/guldum_net)** (22k+ posts) & **[YouTube](https://www.youtube.com/@guldum)**.

## Graveyard (Retired Projects)

Older weekend experiments that had their run:

<ul class="archive-list">
  <li>Eksi Redditify (Chrome extension)</li>
  <li>DailyOW — Overwatch highlights on Instagram (+1k posts) &amp; Tumblr</li>
  <li>İşimi Bul — Job search engine for Turkey (5k users) &amp; Android app</li>
  <li>Just Read — Pocket-style article reader (Web, Android, Chrome extension)</li>
  <li>vidimg.net — YouTube thumbnail generator</li>
  <li>Football Highlights Watch &amp; Android app (1.26k users)</li>
  <li>Alterna — Ekşi Sözlük read-only archive</li>
  <li>Selfgram — Photo diary Android app</li>
  <li>Datanews.io — Hacker News for data scientists</li>
  <li>Psikiyatri Toplantıları &amp; Psikoegitim.net — Event timetables</li>
</ul>
