---
published: false
layout: post
category: roundup
title: 'Weekly Roundup 6 #json #rss #nativescript'
---
![](https://devdala.files.wordpress.com/2016/06/b231fc6d-107f-47ce-b109-f00ebf4a881a.jpeg)

*Summer in Dublin, Air lounger is actually working not just some marketing trick*

* Started to watch Game of Thrones stories:
	* (https://www.youtube.com/watch?v=sEcwakbtXG4)
* Rewrote my prayer times application since ramadan is here:
  	* Used [nativescript](https://www.nativescript.org/) which is amazingly good.
    * On the first day of the update of the app I received 158 concurrent users
    * Will write another post regarding the structure of the app.
![]()
![](https://devdala.files.wordpress.com/2016/06/media-20160607.png)
* Change a remote address
	`git remote set-url`
* Realized this: if you try to iframe youtube in a webview in an android app, your app may be rejected by Google Play Store
	* (https://play.google.com/about/privacy-security/#device-and-network-abuse)
* Awesome way of getting JSON out of RSS feeds:
	* `https://query.yahooapis.com/v1/public/yql?q=select%20title%2Clink%2Cdescription%20from%20rss%20where%20url%3D%22**<ENCODED_RSS_URL>**&format=json&diagnostics=true&callback=`
    * There is this option but it's heavily cached
    	* (http://rss2json.com/)
* 
