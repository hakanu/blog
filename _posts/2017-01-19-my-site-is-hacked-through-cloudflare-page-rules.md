---
published: false
layout: post
category: dns
title: 'My site is hacked with an interesting method '
---
I have a small Turkish meme [site](http://guldum.net). It's very simple and easy to maintain.
I use cloudflare for caching, SSL and DNS stuff and I love it.

However, today I realized that my site started to redirect to some weird site which says some random "Your flash is outdated, please update".

* Check chrome network tab - can not see anything because it's a redirect and all info is gone.
* Check domain provider - all good
* Check Cloudflare DNS settings - all good

Last resort I tried to find out the HTTP request call tree.

I'm breaking the redirection URL because I don't want to send them traffic.

```
curl --head guldum.net
HTTP/1.1 301 Moved Permanently
Date: Thu, 19 Jan 2017 17:24:22 GMT
Connection: keep-alive
Set-Cookie: __cfduid=d0af6e03ce78a3a99580dc2bbc87c90c31484846662; expires=Fri, 19-Jan-18 17:24:22 GMT; path=/; domain=.guldum.net; HttpOnly
Location: https://goo.gl/ H41yAy
Server: cloudflare-nginx
CF-RAY: 323bfadaa6ec3470-LHR
```

It has a 301 redirection, it immediately popped up in my mind: Page rules. I checked my cloudflare account and it was there; somebody guessed my password, logged into my account and only changed my page rules to redirect to that goo.gl short URL which is disabled now thankfully.

I filed a ticket to cloudflare immediately because it's hard to believe that hijacker just modified one domain's page rules given that I have a couple of domains managed from cloudflare dashboard.

Meanwhile changed my password and API keys and enabled two factor authentication.

Support was quick, they informed me that the hijacker only modified the page rules and recommended me to change my password and enable 2-factor authentication.

One more tip, you can go to chrome's developer tools network tab and check "Disable cache" and reload the page. Otherwise Chrome wildly caches the 301 redirects. You may keep seeing the same goo.gl redirect for days unless you clean the cache. But this tiny trick fixes that as well.

All good now thankfully, so long!
