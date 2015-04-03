---
layout: post
title: Google Chrome OS kaynak kodları yayında
date: '2009-11-21 18:54:14'
---

<a href="http://devdala.files.wordpress.com/2009/11/googlechromeos.jpg"><img class="aligncenter size-full wp-image-788" title="GoogleChromeOS" src="http://devdala.files.wordpress.com/2009/11/googlechromeos.jpg" alt="" width="435" height="239" /></a>

Gugıl'ın iddialı işletim sistemi Chrome OS'un kaynak kodları  şimdiden yayınlandı. 2 tip olarak karşımıza çıkmakta. Siz kendinize göre olanı indirin:

Birincisi sadece koda bakıp, küçük değişiklikler yapmak isteyenler için(yapılan değişiklikler kayıt edilmez:

<a href="http://build.chromium.org/buildbot/archives/chromiumos-0.4.22.8.tar.gz">Download Google Chrome OS source code </a>

İkincisi geliştirmeye sürekli katkıda bulunmak isteyenler için:

Önce şu adresten Chromium depot tools'u indirin):

<a href="http://sites.google.com/a/chromium.org/dev/developers/how-tos/install-gclient">Download Chromium depot tools</a>

Git ve Chromium araçlarını kullanarak Chromium OS'u Git depolarından indirmek için:

1. Chromium depot tools'u kurun

2. Yerel makinenize git'i kurun
<pre>sudo apt-get install git-core</pre>
1. Chromium repository'nin bir kopyasını alın
<pre><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">mkdir </span></code><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">[</span></code><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">chromiumos]</span></code>
<code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;"><span style="background-color:#ffffff;"><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">cd </span></code><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">[</span></code><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">chromiumos]</span></code></span></span></code>
<code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;"><span style="background-color:#ffffff;"><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">gclient config </span></code><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;">http://src.chromium.org/git/chromiumos.git</span></code></span></span></code>
<code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;"><span style="background-color:#ffffff;"><code><span style="font-family:Consolas, Monaco, 'Courier New', Courier, monospace;"><span style="background-color:#ffffff;">gclient sync</span></span></code></span></span></code></pre>