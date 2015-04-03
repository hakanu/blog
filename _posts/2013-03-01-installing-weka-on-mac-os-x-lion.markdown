---
layout: post
title: Installing Weka on Mac OS X Lion
date: '2013-03-01 09:38:57'
---

<a href="http://devdala.files.wordpress.com/2013/02/vlcsnap-2012-11-03-13h44m10s166.png"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2013/02/vlcsnap-2012-11-03-13h44m10s166.png" width="720" height="404" /></a>

I tried to install <a href="http://www.cs.waikato.ac.nz/ml/weka/">weka</a> which is a great tool for using basic machine learning algorithm. However, every time I tried to install it gave me an error like this
<blockquote>"weka-3-7-9 is damaged and can't be opened." error.</blockquote>
I tried with earlier versions, again same error with different version number.

At the end after some googling I realized that this is new Mac security stuff. Mac OS is not allowing this app to be installed into computer due to not being from an approved developer.

To solve it go to Setting -&gt; Security &amp; Privacy, mark "Allow applications downloaded from" "Anywhere".

Weka dmg can be found here:

<a title="Download weka from sourceforge" href="http://sourceforge.net/projects/weka/" target="_blank">http://sourceforge.net/projects/weka/</a>

<em id="__mceDel"> </em>