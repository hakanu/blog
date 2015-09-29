---
layout: post
title: Ubuntu&#039;da Firefox 3.5 yüklemek/yükseltmek
date: '2009-09-30 20:52:14'
---

<img class="aligncenter size-full wp-image-374" title="devdala_firefox_ubuntu_icon" src="http://devdala.files.wordpress.com/2009/09/devdala_firefox_ubuntu_icon.png" alt="devdala_firefox_ubuntu_icon" width="149" height="149" />

Ubuntu 9.04 şu an en güncel Ubuntu sürümü ve bunun içinde gelen Firefox versiyonu 3.0.3 idi yanlış hatırlamıyorsam. Ancak şu an Firefox'un 3.5.3 sürümü çıkmış durumda ve gayet stabil. Ubuntu'da bu yükseltme işlemi pek de kolay değil. Birkaç başarısız denemeden sonra en sonunda nasıl yapıldığını buldum bu işin. Öncelikle debian pakedi aradım. Ancak bulamadım. Ondan sonra birkaç kez Synaptic Paket Yöneticisi'nden denedim yine olmadı.

İşte yöntem:

1. Öncelikle Firefox'un sitesinden en güncel Firefox versiyonunu indiriyoruz ki şu anda 3.5.3. İndirmek için <a href="http://download.mozilla.org/?product=firefox-3.5.3&amp;os=linux&amp;lang=tr">tıklayın</a>.

2. İndirdikten sonra masaüstünde gözükecektir.Orda dursun şimdilik

3. Eğer Firefox versiyonunuz 3.5.1, 3.5.2 veya başka diğer 3.5.x ise aşağıdaki kodu Uygulamalar -&gt; Donatılar -&gt; Uçbirim yolunu izleyerek terminali açıp yapıştırın ve entera basın
<p style="font-family:Calibri;font-size:11pt;margin:0;" lang="en-US"><strong><span style="color:#000000;">sudo rm /usr/bin/firefox &amp;&amp; sudo dpkg-divert --rename --remove /usr/bin/firefox &amp;&amp; sudo rm -r /opt/firefox</span></strong></p>
Yukarıdak işlemden sonra Firefox'u açıp Yardım -&gt; Mozilla Firefox Hakkında'ya basıldığında çıkan ekranda Firefox versiyonun 3.0.8'e düşürüldüğünü göreceksiniz ki bu Ubuntu 9.04'ün kendi versiyonudur.

4. İkinci adımda masaüstüne indirdiğimiz <span style="color:#ff6600;"><span style="font-family:Verdana,sans-serif;font-size:12px;line-height:20px;"><strong>firefox-3.5.3.tar.bz2 </strong></span></span>klasörü seçilip sağ tıklanır kopyala veya kes komutlarından birine basılır. Ardından Yerler -&gt; Başlangıç dizinine gidilip oraya sağ tıklanıp yapıştırılır.

5. Uygulamalar -&gt; Donatılar -&gt; Uçbirim yolunu izleyerek terminali açıp aşağıdaki kod parçasını yapıştırın ve entera basın
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">if [[ ! -f /usr/bin/firefox ]]; then sudo apt-get update &amp;&amp; sudo apt-get install firefox; fi &amp;&amp; if [[ -e ~/.mozilla ]]; then cp -R ~/.mozilla ~/.mozilla.backup; fi &amp;&amp; sudo tar -jxvf firefox-3*.tar.bz2 -C /opt &amp;&amp; rm firefox-3*.tar.bz2 &amp;&amp; sudo mv /opt/firefox/plugins /opt/firefox/plugins.backup &amp;&amp; sudo ln -s /usr/lib/xulrunner-addons/plugins /opt/firefox/plugins &amp;&amp; sudo dpkg-divert --divert /usr/bin/firefox.ubuntu --rename /usr/bin/firefox &amp;&amp; sudo ln -s /opt/firefox/firefox /usr/bin/firefox</span></p>
6.Ve Firefox'u yeniden başlatın. İsterseniz Yardım -&gt; Mozilla Firefox Hakkında'ya basıp versiyonuna bakabilirsiniz. 3.5.3 olduğunu göreceksiniz