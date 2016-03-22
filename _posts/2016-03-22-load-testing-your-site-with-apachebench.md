---
published: false
layout: post
category: python
title: Load testing your site with ApacheBench
---

* Install 
sudo apt-get install apache2-utils

* Run, don't forget trailing /
ab -n 1000 -c 100 http://hakanu.net