---
published: false
layout: post
category: python
title: "Weekly Roundup - 2"
---


![](https://devdala.files.wordpress.com/2016/03/pano_20140510_212720.jpg)

*2015, Dublin - Oneplus One*

*"The ones that love us never really leave us".*
(Sirius Black (Harry Potter))

* Internet is broken by an angry programmer who is totally right:
  * [I’ve Just Liberated My Modules](https://medium.com/@azerbike/i-ve-just-liberated-my-modules-9045c06be67c#.f0zgycwl7)
  * [A discussion about the breaking of the Internet](https://medium.com/@mproberts/a-discussion-about-the-breaking-of-the-internet-3d4d2a83aa4d#.t0oxvjce2)
  * [Business insider explains the situation simply](http://uk.businessinsider.com/npm-left-pad-controversy-explained-2016-3?r=US&IR=T)
  
* For people who uses npm for left-pad which was unpublished by Azer, can do this for fixing the builds: (Because code is still in github; just not in npm anymore)
```
"dependencies": {
    "left-pad": "git+ssh://git@github.com:azer/left-pad"
}
```
OR shortcut:
```
"dependencies": {
  "left-pad": "azer/left-pad"
}
```

* Situation on the npm side:
*Fun fact: because of all the metadata, the javascript community downloads "isarray" in the excess of 100GB a month from npm. For a one liner*
[Tweet](https://twitter.com/mitsuhiko/status/712624914071728128)

* More JS comedy when it's digged deeper:
  * [Tweet](https://twitter.com/TobyKurien/status/712536641391484929)
  * [Reddit](https://www.reddit.com/r/programming/comments/4bjss2/an_11_line_npm_package_called_leftpad_with_only/)
![](https://pbs.twimg.com/media/CeNwPEsXEAABcPl.jpg)

* "Saturday night data mining: #golang contributors by date"
  * [Tweet](https://twitter.com/davecheney/status/711147776332079104)
![](https://pbs.twimg.com/media/Cd6BIiPUAAABjco.jpg)

* New trend: Reply everything with "willing to relocate San Francisco"
  * [Source](https://twitter.com/search?f=tweets&vertical=default&q=%22willing%20to%20relocate%20to%20san%20francisco%22&src=typd)
  
* [NPM & left-pad: Have We Forgotten How To Program?
](http://www.haneycodes.net/npm-left-pad-have-we-forgotten-how-to-program/)

* 