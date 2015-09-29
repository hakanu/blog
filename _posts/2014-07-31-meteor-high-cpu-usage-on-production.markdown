---
layout: post
title: Deploying Meteor and high cpu usage on production
date: '2014-07-31 22:43:19'
---

![](http://res.cloudinary.com/hakanu/image/upload/c_scale,w_573/v1406846290/vlcsnap-2014-07-20-05h08m05s44_za2ygz.png)

Meteor is an open source javascript framework which gives developers to create real time Web apps without dealing with server code. 
From my side it's a lot like firebase. However there are slight differences between them. Firebase also supports server side data synchronisation.
Even though I don't really like nodejs, I tried to play with meteor. The reason why I dislike Nodejs is because I hate npm. It never works perfectly, there is always something missing etc. I need to a lot of stackoverflowing to understand the errors. Same here again, I've faced a couple of problems but at the end I made the app run. Everything was good until I deployed the app to a production environment. By the way I will talk about painful deployment process as well.
First of all you need to have these two installed in your machine to make meteor apps run:

* Meteor `curl https://install.meteor.com/ | sh`
* Meteorite: 
`npm install -g meteorite`
If the code above does not work, try this (welcome to nodejs world):
`sudo -H npm install -g meteorite`

From now on, you can replace all of the meteor commands with mrt (eg `meteor blah` with `mrt blah`). Cool isn't it? Well I guess :-O.

In order to deploy the project you need to create a bundle first according to the deployment [guidelines](http://docs.meteor.com/#deploying):
`meteor bundle myapp.tgz`
`PORT=3000 MONGO_URL=mongodb://localhost:27017/myapp node bundle/main.js`

Ok, so what's the problem here?

If you see this error, you should run this command:
`mrt bundle myapp.tgz`
`tar -zxvf myapp.tgz`
And then start the app:
`PORT=3000 MONGO_URL=mongodb://localhost:27017/myapp node bundle/main.js`

No wait, what about this error now?

By the way, I should explicitly say that according to my observations, bundle command creates the package only specific to the given environment. So it may change when you develop on windows and deploy onto the linux machine.

So what about the error? The weird thing is that my local version works perfect and creates the bundle. Here is the solution, get a better production machine. bundle command uses ram around ~400mb(my observations again, might be wrong). If you don't have enough space in the memory, it kills itself without giving a proper error message. It was painful to find this out.

Awesome, so I made the app run. All good in the hood, let's send a couple of requests to our production IP and then check the server logs and load. Surprisingly, CPU stuck at 20% all the time, every second. My first reaction was 'hmm, nodejs is supposed to be non blocking and faster and lighter'. According to the articles I read about 'nodejs on production', people (eg ebay) were extremely happy with the decreasing server load after being migrated to the nodejs. It was not working for me. I deep-dived and understood that meteor has this hot code push feature. When you edit the code and hit ctrl+S, it refreshes the webapp tab. Great but this is useful in the development environment. This also made my laptop sound like an airplane. Apparently there is a problem with the file watchers. I needed to change the environment to production by using environment variables.

As you can see, green is the user CPU load on the server which is constantly at 20% for whole day, every second. After that I started to use node production environment variables, and the cpu load became less than 1%.
![](http://res.cloudinary.com/hakanu/image/upload/v1406845593/Screenshot_from_2014-07-31_23_25_38_fkhska.png)

[Cloudflare](http://cloudflare.com) does not support websockets. So you may want to disable websockets. Or you can simply bypass the cloudflare network which will make you lose CDN capabilities of cloudflare.

If you would like to give a try to what I did, here it is:
#### [Paylas.io - A real time link sharing platform](http://paylas.io)