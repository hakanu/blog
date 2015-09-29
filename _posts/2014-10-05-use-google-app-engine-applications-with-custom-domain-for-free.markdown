---
layout: post
title: Use Google App Engine Applications with Custom Domains for free
date: '2014-10-05 12:38:17'
---

[![](http://distilleryimage9.ak.instagram.com/6e913f366d6611e2a96422000a1fbc12_7.jpg)](http://instagram.com/uhakan)

I like free. Looked for a good resource to achieve this. However, most of them are outdated and they say that to be able to use GAE apps with custom domain, you need a Google Apps account no you don't. Plus, if you add your appid.appspot.com to your clouflare connected domain, app engine does not authorize the connection and redirects domain to google.com's main page. It's pretty weird but expected. In heroku, it's really easy to allow custom domains and point them to your appid.herokuapp.com address from cloudflare by using its DNS flattening feature.
Ok here are the steps to do that on app engine.

* Buy a domain, [here is my fave]()
* Finish your app from [Google App Engine](https://appengine.google.com/)
* Go to [new Google Cloud Console](https://console.developers.google.com), not old app engine console.
* Choose project and Compute -> App Engine -> Settings -> Custom domains (Yes it's kinda secret). 
* You will be able to see all of your domains you own from [Google Webmaster Tools](https://www.google.com/webmasters/tools/)
* If your desired domain is already in Google Webmaster Tools, choose the one you want to use. Otherwise go to Webmaster tools and connect your domain first and come back here. You can add your domain by modifying cloudflare DNS entries or whatever provider you have.
* Here is my stuff for one of my apps: http://kampanyalar.me/
* The thing is that it's a little bit slower than appid.appstpo.com (~200 ms vs ~400 ms).

[Source](https://cloud.google.com/appengine/docs/domain)