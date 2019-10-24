---
layout: post
title: Adding Netlify admin CMS to my Jekyll blog living at Github
type: Meta
categories:
  - Meta
tags:
  - Meta
image: /assests/img/ac5c5be6-b719-4403-9e67-b012db7b4cb5.jpeg
description: Test post from netlify admin
date: 2019-10-24T11:01:46.379Z
---
I have been blogging since 2009 where there was no microblogging. I was usually dumping my notes about Adobe Flash to the blog in case it's useful for people. Nothing changed since then, after ~10 years, I have around 470 markdown files. 

My journey was like this:

* 2009 - Wordpress.com with subdomain 
* 2010 - My own wordpress hosting with some php host
* 2014 - [Ghost](http://ghost.org) self hosted @ heroku - still my favorite env for blogging. 

[Migrated my blog from Wordpress to Ghost](https://hakanu.net/2014/07/06/migrating-to-ghost-from-wordpress/)
* 2015 - Static websites became cool again, Github Pages was  in town, why not using it?

[Migrated my blog from Ghost to Github pages](https://hakanu.net/2015/05/03/migrate-blog-from-ghost-to-github-pages/)
* Since 2015, I have been using jekyll + github pages setup. Zero downtime, nothing unpredictable, no npm dependency fail (ghost loves this error), no php security vulnerability issue forcing me to update wordpress.

My blogging performance (purely trying if markdown table will render from this admin view)

| Year| # of posts |
| --- | ----------- |
| 2009 | 158|
| 2010 | 176|
| 2011 | 31|
| 2012 | 22|
| 2013 | 9|
| 2014 | 17|
| 2015 | 14|
| 2016 | 23|
| 2017 | 11|
| 2018 | 12|
| 2019 | 4|

Nowadays I was looking at JAMStack, it's nothing new. I have built many websites based on jekyll + firebase + github pages (or surge.sh); all static using some auth provider (back4app, firebase, parse RIP etc). However, JAMStack and Netlify make it more legit by providing necessary api endpoints easily in cooperation with git gateways. 

My biggest problem while blogging is not having a proper writing environment. Wordpress has awesome tooling; ghost has great builtin UI to write posts with instant preview; however, jekyll has nothing; i need to use my favorite editor and git push to gh-pages branch. OK while this is pretty cool when you have laptop in your disposal at any given time. I'd like to quick post something from browser directly where i don't have access to terminal. In order to do that I was using prose.io which is an editor authenticates itself for your github and commits markdown to your repo. That was the best one so far and I have used a ton. It was an MVP, not so much UX, not much new development but it was ok. 

Recently I have discovered netlify CMS which is a generic admin UI (some js + html magic), you add it under an admin folder, and you set up identity from <https://app.netlify.com> and boom it gives you: user login, user email verification, user email invites and highly modifiable admin panel. Now I'm writing this post from that UI. It also gives you chance to upload images. 

Here are the setup instructions:
<https://www.netlifycms.org/docs/jekyll/>

You can use it with almost all of the static website builders: Hugo (tried and working well), Middleman, Gatsbyjs...

I didn't touch my posts at all; they still live in github and whenever I commit any changes; whole website is rebuilt and deployed through netlify and all for free with identity API (admin user login).

No performance hit after the move:

```
curl -s -w \
'Website Response Time for :%{url_effective}\n\nLookup Time:\t\t%{time_namelookup}\nConnect Time:\t\t
%{time_connect}\nPre-transfer Time:\t%{time_pretransfer}\nStart-transfer Time:\t%{time_starttransfer}\n\nTotal Time:\t\t%{time_total}\n' \
-o /dev/null \
https://hakanu.net
```

Website Response Time for :https://hakanu.net

Lookup Time:            0.034084
Connect Time:           0.118848
Pre-transfer Time:      0.930033
Start-transfer Time:    1.308011

Total Time:             1.315497
