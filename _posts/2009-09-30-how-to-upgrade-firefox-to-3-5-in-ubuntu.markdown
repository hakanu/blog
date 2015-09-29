---
layout: post
title: How to upgrade Firefox to 3.5 in Ubuntu
date: '2009-09-30 21:26:47'
---

<img class="aligncenter size-full wp-image-374" title="devdala_firefox_ubuntu_icon" src="http://devdala.files.wordpress.com/2009/09/devdala_firefox_ubuntu_icon.png" alt="devdala_firefox_ubuntu_icon" width="149" height="149" />

Ubuntu 9.04's default Firefox version is 3.0. However, nowadays the latest relase of Mozilla Firefox is 3.5.3. In Linux systems like Ubuntu it is hard to install or upgrade programs not similar to Windows operating systems. By the way, Mozilla Firefox has no 3.5.3 debian package. So the upgrade operation becomes harder.

Here is the way to upgrade/install Mozilla Firefox 3.5 in operating system Ubuntu

1. Firstly you must download the latest version of Firefox from its official web site. While I was writing this post, the latest version was 3.5.3.

<a href="http://download.mozilla.org/?product=firefox-3.5.3&amp;os=linux&amp;lang=tr">Click here to download Mozilla Firefox 3.5.3</a>

2. If your system has Firefox 3.5.x(3.5.1 or 3.5.2) paste the code below to Terminal and press enter button.(To open terminal: Application -&gt; Accessories -&gt; Terminal)
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0;">sudo rm /usr/bin/firefox &amp;&amp; sudo dpkg-divert –rename –remove /usr/bin/firefox &amp;&amp; sudo rm -r /opt/firefox</p>
After this operation, open Firefox and follow this path Help -&gt; About Mozilla Firefox.  There will be a window that is written that your Firefox version is downgraded to 3.0.8.

3. Next step is to move the file that was downloaded and placed on our Desktop named <span style="color:#ff6600;"><span style="font-family:Verdana,sans-serif;font-size:12px;line-height:20px;"><strong>firefox-3.5.3.tar.bz2 </strong></span></span>Copy or cut this file from here and paste it to your Home folder. To reach it follow this path: Places -&gt; Home

4. open the terminal by following this path: Application -&gt; Accessories -&gt; Terminal and paste this code below. After that press enter button
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0;">if [[ ! -f /usr/bin/firefox ]]; then sudo apt-get update &amp;&amp; sudo apt-get install firefox; fi &amp;&amp; if [[ -e ~/.mozilla ]]; then cp -R ~/.mozilla ~/.mozilla.backup; fi &amp;&amp; sudo tar -jxvf firefox-3*.tar.bz2 -C /opt &amp;&amp; rm firefox-3*.tar.bz2 &amp;&amp; sudo mv /opt/firefox/plugins /opt/firefox/plugins.backup &amp;&amp; sudo ln -s /usr/lib/xulrunner-addons/plugins /opt/firefox/plugins &amp;&amp; sudo dpkg-divert –divert /usr/bin/firefox.ubuntu –rename /usr/bin/firefox &amp;&amp; sudo ln -s /opt/firefox/firefox /usr/bin/firefox</p>
5. Restart Firefox. If you look at its version by clicking Help -&gt; About Mozilla Firefox, you will see 3.5.3