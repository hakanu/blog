---
layout: post
title: 20th International Obfuscated C Code Contest
date: '2012-04-19 21:07:53'
---

What can 33 lines of code do? Ray tracing?

Here are the rules:
<ul>
	<li>To write the most Obscure/Obfuscated C program within the rules.</li>
	<li>To show the importance of programming style, in an ironic way.</li>
	<li>To stress C compilers with unusual code.</li>
	<li>To illustrate some of the subtleties of the C language.</li>
	<li>To provide a safe forum for poor C code.</li>
</ul>
I compiled and tried this one:

<a href="http://www.ozone3d.net/public/jegx/201204/ioccc-zucker-text-raytracing.jpg"><img class="aligncenter" src="http://www.ozone3d.net/public/jegx/201204/ioccc-zucker-text-raytracing.jpg" alt="" width="650" height="615" /></a><em><a href="http://www.ioccc.org/2011/zucker/hint.html">Text raytracer</a> | <a href="http://www.ioccc.org/2011/zucker/zucker.c">source code</a></em>

Compile it:
<pre>gcc -o zucker zucker.c -lm</pre>
*-lm for linkin math library. Otherwise functions like atan would give error:
<blockquote>zucker.c:(.text+0x43b): undefined reference to `atan2'
zucker.c:(.text+0x5ae): undefined reference to `sin'
zucker.c:(.text+0x5ce): undefined reference to `cos'
zucker.c:(.text+0x9bf): undefined reference to `sqrt'
/tmp/ccRJ0Y3C.o: In function `main':
zucker.c:(.text+0x14c4): undefined reference to `pow'
zucker.c:(.text+0x170b): undefined reference to `pow'</blockquote>
<pre>./zucker &gt; hello.ppm</pre>
Or we can give the text to write:
<pre>./zucker "hakan" &gt; hello2.ppm</pre>
Here is the pic created (it is taking a little long don't worry - it was ppm but i changed it to png):

<a href="http://devdala.files.wordpress.com/2012/04/dev.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/04/dev.png" alt="" width="600" height="220" /></a>

There is also another one (im too lazy to  try this one):

<a href="http://www.ozone3d.net/public/jegx/201204/ioccc-akari-downsampler.jpg"><img class="aligncenter" src="http://www.ozone3d.net/public/jegx/201204/ioccc-akari-downsampler.jpg" alt="" width="700" height="751" /></a><em><a href="http://www.ioccc.org/2011/akari/hint.html">Downsampler with 3 embeded programs</a> | <a href="http://www.ioccc.org/2011/akari/akari.c">source code</a></em>