---
published: false
layout: post
category: markdown
title: Switched to Redcarpet instead of kramdown as markdown renderer
---

Redcarpet is the engine written in C by Github, It's also known as Github flavored markdown. I've been using kramdown since the beginning but apparently redcarpet has some cool features like autolinking.

For example if you put a link in your post without using `<url>` notation or `[url text](url)`, kramdown does not convert those urls into `<a>` tags. Instead it renders them as raw text in `<p>` tag.

Here is my config.yaml:

```# Build settings
#markdown: kramdown
markdown: redcarpet
kramdown:
  input: GFM
  hard_wrap: false
redcarpet:
  extensions: ["autolink", "fenced_code_blocks"]```
  
Here is the full list of available redcarpet extensions:
https://github.com/vmg/redcarpet