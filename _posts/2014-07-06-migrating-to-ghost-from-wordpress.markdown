---
layout: post
title: Migrated my blog from Wordpress to Ghost
date: '2014-07-06 23:04:33'
---

Yay, happy days. It has been in my todo list since I saw [ghost's kickstarter campaign](https://www.kickstarter.com/projects/johnonolan/ghost-just-a-blogging-platform). They pledged ~200k pounds while expecting 25k.

Whatever, first I set up a free account from [ghost's official website](http://ghost.io) and then tried to write my first blog post. I was amazed with the typing experience. Admin side was extremely clean; markdown was simply beautiful and fun to write.

Don't get me wrong, I really like wordpress as other [60%](http://w3techs.com/technologies/details/cm-wordpress/all/all) of the websites on the internet. The problem is that I don't like php and I don't like my hosting company. Although it's easy to find a php hosting company, I lose all of the control. Wordpress is so complicated to manage. I also have a lot of historical problems from earlier versions of wp. I should start with a clean slate. Ghost's simplicity hit me in the heart.

Ok, so here are the basic steps:

* Find a hosting company for nodejs (eg [heroku](heroku.com)). Or setup your own environment by creating a VM using amazon's free tier account or digital ocean's basic plan which is $5 per month. Pretty cheap.
* Download the [source code](https://ghost.org/download/) of ghost.
* If you go with your own VM, setup nodejs and scp ghost files into that VM.
* If you go with heroku, follow [these steps](https://devcenter.heroku.com/articles/getting-started-with-nodejs) to run nodejs.
* When you make it run on your VM, grab your IP:Port pair to connect your ghost hello page.
* When you make it run on heroku, grab your heroku application path pair to connect your ghost hello page.
* [Cloudflare](http://cloudflare.com) will be the best option in this case. Because it supports DNS flattening which makes you reach heroku application addresses from domains names. And it's completely free. Awesome!
* When you are ok with ghost installation, go to your admin panel from http://yourblog.com/ghost
* Signup with your details. Don't worry, ghost only allows one person to write for now. So even though other people comes to that page, they won't see registration.
* Import your posts! Fun part. Navigate to http://yourblog.com/ghost/debug/, you will see json import. It looks pretty straightforward isn't it?
* Use this [wordpress plugin](https://wordpress.org/plugins/ghost/) to export your posts from wp blog as json.
* When you are done, try json with that debug page. In my case it didn't work :/
* First problem was the upload size. I had a lot of posts in my wp blog. So they exceed ghost's upload size. When I divide the json into pieces. It failed again with some RejectionError during the upload which is like this:
![RejectionError message](http://devdala.files.wordpress.com/2014/05/screen-shot-2014-05-26-at-16-43-08.png)
Exact error messages:
- RejectionError: current transaction is aborted, commands ignored until end of transaction block
- js console: POST http://yourblog.com/ghost/api/v0.1/db/ 503 (Service Unavailable)

* I also explained the same problem [here](https://ghost.org/forum/using-ghost/8433-wordpress-migration-json-file-import-failing-with-unknown-error/) on ghost forum.
* So the problem was that some of the posts don't have published_at attribute. This breaks ghost importing. I wrote a small python script to fix the json and make it more friendly for ghost. You can find it here as a gist with a detailed explanation of the problem:
https://gist.github.com/hakanu/466a5304522fd2a0fb98
* After you did this, you are almost done. Two more steps left. First one is the google analytics. For this you need to go to the theme's folder (content>themes>casper>default.hbs) and add your tracking code in somewhere between <head> </head> tags. It's pretty easy.
* And last step is the comments which I'm not so successful to achieve:) The recommended way is to use the disqus and import all of the comments from wp to disqus. After that connect disqus to ghost by following [this tutorial](https://help.disqus.com/customer/portal/articles/1454924-ghost-installation-instructions). I did but my comments are not showing up for some reason. I will figure out later. I don't get many comments so I don't worry about it.
* Ghost makes your links same as wordpress so your old links won't be broken. In my case, I needed to enable settings, "Dated permalinks". The permalink format became same as wordpress.
* You can find a nice benchmark [here](http://www.appdynamics.com/blog/nodejs/an-example-of-how-node-js-is-faster-than-php/) how ghost outperforms wordpress.
* By the way, by default ghost uses sqlite so you can freely host it in amazon with your tiny sqlite db. If you go for heroku, you can use it with fully managed heroku postgres. Ghost supports mysql and postgres natively.

> **Finally, Ghost rocks**!

