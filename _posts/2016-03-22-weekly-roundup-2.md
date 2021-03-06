---
published: true
layout: post
category: roundup
title: "Weekly Roundup - 2 #npm #npmgate #go #ai"
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
  * [Defence from NPM side about one line modules](https://github.com/sindresorhus/ama/issues/10#issuecomment-117766328)
  
* Microsoft's AI backed tweetbot melted down after 24 hours of learning.
  * http://www.telegraph.co.uk/technology/2016/03/24/microsofts-teen-girl-ai-turns-into-a-hitler-loving-sex-robot-wit/
![](http://www.telegraph.co.uk/content/dam/technology/2016/03/24/Microsoft_Tay_daddy-large_trans++qVzuuqpFlyLIwiB6NTmJwfSVWeZ_vEN7c6bHu2jJnT8.jpg)

* Cloudflare's library CDN links. Lots of goodies are here for production environment (React, Angular, Bootstrap, Jquery)
  * https://cdnjs.com/libraries
  
* Apple's iPhone recycling robot Liam, it only takes 11 seconds
  * https://twitter.com/verge/status/713115617411227648?s=09

* 