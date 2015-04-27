---
layout: post
title: Getting Geo Location of Web site visitor with javascript
date: '2015-04-27 16:31:13'
---

It's really short javascript code.

You can test it in the js console of Chrome or your favorite browser:

`navigator.geolocation.getCurrentPosition(function(position){
		console.log(position.coords.latitude + " | " + position.coords.longitude)});`

It will print the geo location coordinates in latitude and longitude format. Of course you need to allow when it's prompted for location permission.