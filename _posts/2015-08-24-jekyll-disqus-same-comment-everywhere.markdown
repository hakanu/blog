---

layout: post
category: jekyll
author: Hakan Uysal
title: Solving Disqus comment problem on Jekyll - same comments everywhere
date: '2015-08-24 23:31:13'

---


I have been using [Disqus](http://disqus.com) in order to handle blog comments for a long time. I was also using it when I was with Ghost. It's a great and good looking way to handle comments. It makes your blog more mobile. It has one downside which is that the comment box is iframe so I don't think it's good for SEO.

Disqus's own help center:

* [Why are the same comments showing up on multiple pages?](https://help.disqus.com/customer/portal/articles/662547-why-are-the-same-comments-showing-up-on-multiple-pages-)

* [JavaScript configuration variables](https://help.disqus.com/customer/portal/articles/472098-javascript-configuration-variables)

With this light here is my disqus snippet in my jekyll code:

`<div id="disqus_thread"></div>`

`<script type="text/rocketscript">`

`  var disqus_shortname = 'YOUR_USERNAME';`

`  var disqus_identifier = '{{ page.url }}';`

`  var disqus_url = '{{ site.url }}{{ page.url }}';`

`  var disqus_title = '{{ page.title }}';`

`  var disqus_category_id = '{{ post.category }}';`

Trick is assignin a unique identifier to the disqus_identifier javascript variable. In our case page.url is pretty unique. And also we are not supposed to assign same thing to disqus_identifier and disqus_url. So url is the full url with site info, identifier is the relative path.


Enjoy!