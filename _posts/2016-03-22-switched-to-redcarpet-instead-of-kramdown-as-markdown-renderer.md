---
published: true
layout: post
category: markdown
title: Redcarpet instead of kramdown as markdown renderer
---

![Vieux Port de Montréal](https://devdala.files.wordpress.com/2016/03/p51017-121508-pano.jpg)

*Vieux Port de Montréal, October 2015 - Oneplus one*

Redcarpet is the engine written in C by Github, It's also known as *Github flavored markdown*. I've been using kramdown since the beginning but apparently redcarpet has some cool features like autolinking.

For example if you put a link in your post without using `<url>` notation or `[url text](url)`, kramdown does not convert those urls into `<a>` tags. Instead it renders them as raw text in `<p>` tag.

Here is my config.yaml:

```
markdown: redcarpet
kramdown:
  input: GFM
  hard_wrap: false
redcarpet:
  extensions: ["autolink", "fenced_code_blocks"]
```
  
Here is the full list of available redcarpet extensions:
https://github.com/vmg/redcarpet

Btw **fenced codeblocks** kicks ass, just put your code like this:

  \`\`\`
  
  foo.bar()
  
  \`\`\`
