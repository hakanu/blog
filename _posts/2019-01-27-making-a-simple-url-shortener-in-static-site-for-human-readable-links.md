---
published: true
layout: post
category: python
title: Making a simple url shortener in static site for human readable links
---
There are many url shortening services which either look very ugly and hard to use or impossible to find a good short suburl. Everything is already taken :/

I was thinking about writing my own shortener with around 100 lines of python max but I felt so lazy and don't want to maintain hosting yet another server.

Some jekyll extensions that github-pages support are published on this topic, but I don't want to install any more extensions so I have ended up in this quick solution with not-so-elegant js redirect. You can also go for meta tags for redirection.

These steps assume that you already have a static site either built with jekyll or plain html serving. If you don't have it, you can start building from [here](https://jekyllrb.com/) and publish it for free with [github pages](https://pages.github.com/) or [gitlab pages](https://about.gitlab.com/product/pages/). You don't have to use jekyll at all.

* Create a file in the root folder with html extension => test.html
* Add this as content, changes href to your destination

```html
<html>
<body>
  <h1>Redirecting...</h1>

  <script>
  	window.location.href = "DESTINATION_URL";
  </script>
</body>
</html>
```

* Push the changes to your github or gitlab pages.
* Go to https://domain/test (jekyll automatically drops .html extension) => see the redirection to DESTINATION_URL.

Example:
hakanu.net/test => https://www.google.com/search?source=hp&ei=dKhOXN2LK4ie_QayzqiYBw&q=hakanu.net&btnK=Google+Search&oq=hakanu.net&gs_l=psy-ab.3...334.1456..1506...0.0..0.109.932.1j8......0....1..gws-wiz.....0..0i131j0j0i10j0i10i30j0i5i30j0i5i10i30.wBEQibgZi3s

	Downside of this solution is that there is no metrics of the link usage :-O.