---
published: false
layout: post
category: roundup
title: 'Weekly roundup 8 - #pokemongo #oneplus'
---
* Oneplus 3 is awesome, the best phone I've ever used so far. And it's amazingly fast after Nexus 6p. 
* Pokemon Go still going strong, here is the map created by consuming information from directly Niantic's servers:
	* <https://github.com/AHAAAAAAA/PokemonGo-Map>
* Duckduckgo thinks Telegram is not secure
![](https://pbs.twimg.com/media/CopP0O-UkAAyy5W.jpg:large)
* Postgres team discussed the Uber's migration from Postgres to MySQL
	* <https://www.postgresql.org/message-id/5797D5A1.5030009%40agliodbs.com>
    * This was Uber's [original post](https://eng.uber.com/mysql-migration/)
    * [Cool discussion](https://news.ycombinator.com/item?id=12201353) in Hacker News about how postgres acted mature instead of replying back each claim.
    * By the way, TIL: postgres is the successor of Ingress which is the core developer's first rdbms. So it's name is coming from post-ingress.
* This week I dedicated some time reading Language Translation with Machine Learning by using Natural Language Processing.
	* [Rough chart](http://language.worldofcomputing.net/category/machine-translation)
    ![](http://language.worldofcomputing.net/wp-content/uploads/2010/11/machine-translation-process1.JPG)
* Weird Jekyll update
	* My blog was down for a couple of hours because I purged my cloudflare cache. Apparently after that scss compiler didn't kick in and re-build my css file. So blog looked soo ugly.
    * The reason for that is Jekyll compiler now needs scss files to have this prepended:

`---
---
@charset "utf-8";
$base-font-family: 'Quicksand', sans-serif;`

	* I didn't have those 2 lines of dashes and my css was not built. Now we are all good.
    * [Solution Source](https://github.com/jekyll/jekyll-help/issues/104)
* Whole purpose of this css battle was for changing font of the blog. I switched from Inconsolate to QuickSand which is inspired by Medium.com.
	* https://www.google.com/fonts/specimen/Quicksand
* Pokemon Go: 100 million downloads, $10M per day. [source](http://www.androidauthority.com/pokemon-go-100-million-installs-10-million-daily-revenue-706885/)
* Github open sourced their battle-tested MySQL schema migration tool:
	* https://github.com/github/gh-ost
* Instagram Stories are out!
	* Stats are cool
    * Audience is there
    * Shiny pens are cool
    * No dog filters yet :-O
    * No location, time, slo-mo, fast-mo or speed filters etc.
* Read Jack Dorsey (Square and Twitter CEO) routine and tried it this week. Really works!
	<http://uk.businessinsider.com/jack-dorsey-wakes-up-at-5-in-the-morning-to-meditate-2015-12?r=US&IR=T>
	* ![](http://static4.uk.businessinsider.com/image/564df103dd089507548b4661-480/jack-dorsey.jpg)
    * [My 7 minute workout app](https://play.google.com/store/apps/details?id=com.popularapp.sevenmins)
* 
