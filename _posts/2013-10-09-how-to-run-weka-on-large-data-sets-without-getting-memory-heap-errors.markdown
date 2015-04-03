---
layout: post
title: How to run Weka on large data sets without getting memory heap errors?
date: '2013-10-09 22:23:55'
---

I guess Weka is the official tool of each Msc in CS student.

I was trying to work with Weka on a relatively large data, ~50k rows, it gave me this java heap error. The trick is running weka with an additional flag.

By default its memory is less than 128mb I guess, I was generous and gave 1024mb, you can tweak it according to your computer's memory plus your task's consumption
<blockquote>
<pre>java -jar we<em id="__mceDel">ka.jar -Xmx1024m</em></pre>
</blockquote>