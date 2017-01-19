---
published: false
layout: post
category: dns
title: My site is hacked through Cloudflare page rules
---
I have a small Turkish meme [site](http://guldum.net). It's very simple and easy to maintain.
I use cloudflare for caching, SSL and DNS stuff and I love it.

However, today I realized that my site started to redirect to some weird site which says 

* Check chrome network tab - can not see anything because it's a redirect and all info is gone.
* Check domain provider - all good
* Check Cloudflare DNS settings - all good

Last resort I tried to find out the HTTP request call tree.

# I'm breaking the redirection URL because I don't want to send them traffic.

curl --head guldum.net
HTTP/1.1 301 Moved Permanently
Date: Thu, 19 Jan 2017 17:24:22 GMT
Connection: keep-alive
Set-Cookie: __cfduid=d0af6e03ce78a3a99580dc2bbc87c90c31484846662; expires=Fri, 19-Jan-18 17:24:22 GMT; path=/; domain=.guldum.net; HttpOnly
Location: https://goo.gl/ H41yAy
Server: cloudflare-nginx
CF-RAY: 323bfadaa6ec3470-LHR
