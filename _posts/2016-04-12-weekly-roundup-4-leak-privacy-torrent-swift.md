---
published: true
layout: post
category: roundup
title: "Weekly roundup - 4 #leak #privacy #torrent #swift"
---




![](https://devdala.files.wordpress.com/2016/04/img_20151217_174337-pano-compressor.jpg)

*A panorama night shot with Nexus 6p, 2015*

* Apple use swift only in calculator app in iOS. 
	* https://medium.com/@ryanolsonk/is-apple-using-swift-4a6c80f74599#.d35wfcl91
* Turkish citizenship data leaked (50m records)
![](https://pbs.twimg.com/media/CfMQMaeWEAA7iuK.jpg:large)
	* https://twitter.com/dchest/status/716934572949299200
* Panama Papers leak
* ng-infinite-scroll CDN
	* https://cdnjs.cloudflare.com/ajax/libs/ngInfiniteScroll/1.2.2/ng-infinite-scroll.min.js
* Easiest terminal torrent client: Aria2c
	* `wget http://example.com/some.torrent`
    * `sudo apt-get install aria2`
    * `aria2c some.torrent`
* Today I learnt (TIL), there is a neo4j alternative developed by a Googler:
	* https://github.com/google/cayley
* Read large files with python without pullling whole file into memory
```
with open("log.txt") as infile:
    for line in infile:
        do_something_with(line)
```
* Impressive: **Grindr** Manages More than 1,800,000 API Calls Per Minute with Less than 5 Engineers - What do they use? App Engine?
	* http://get.treasuredata.com/WBN-2016-04-15-Grindr
    * Other impressive metrics
    	* 900MM API Calls per day
		* 65MM Chat Messages per day
		* 10k Geo Spatial database operations per second
		* 300k Profile Image upload per day
		* 2MM Chat Images exchanged per day
        * [Source](http://stackoverflow.com/jobs/companies/grindr)
* Interesting presentation on linux filesystem - Trials with 1 billion files
	* http://events.linuxfoundation.org/slides/2010/linuxcon2010_wheeler.pdf
* [Sia - Cheap thrills](https://www.youtube.com/watch?v=nYh-n7EOtMA) video is awesome
* [Macklemore - Dance off](https://www.youtube.com/watch?v=UwsR5LC0mII) - i guess this is unofficial
