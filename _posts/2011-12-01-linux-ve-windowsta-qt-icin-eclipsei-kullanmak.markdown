---
layout: post
title: Linux ve Windows'ta Qt için Eclipse'i kullanmak
date: '2011-12-01 14:14:23'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/11/lisa-hannigan-knots-official-hd-video-mp4_20111122_012258-096.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/11/lisa-hannigan-knots-official-hd-video-mp4_20111122_012258-096.jpg" alt="" width="691" height="389" /></a></p>
<p style="text-align: center;">Yazılara alakasız resim koyma konusunda gittikçe başarım artıyor.</p>
Minimum gereksinimler:
<ul>
	<li>Windows ve Linux</li>
	<li>Eclipse 3.2.1 veya daha yeni bir surum</li>
	<li>Eclipse C/C++ CDT Plugin 3.1.1 veya daha yeni bir surum</li>
	<li>Qt 4.1.0 veya daha yeni bir surum</li>
	<li>Java JRE 1.4 veya daha yeni bir surum</li>
</ul>
Eger Microsoft toolchainleri kullaniliyorsa debugging biraz kisitli. En iyi mingw ile calisiyor.

Yukleme:
<ul>
	<li>Eclipse C/C++ indirilir - <a href="http://www.eclipse.org/downloads/">http://www.eclipse.org/downloads/</a></li>
	<li>Eclipse Qt integration indirilir (Official Qt distribution) - <a href="http://qt.nokia.com/products/eclipse-integration/">http://qt.nokia.com/products/eclipse-integration/</a></li>
	<li>Eger Qt API documentation istiyorsaniz ki bence isteyin, onu da ayni yerden indirilir. Eclipse Qt API Documentation.</li>
	<li>Linux icin Sun java runtime gerekli. Openjdk olmuyor sanirim.</li>
	<li>Eclipse'i bir yere cikarilir(tar'dan veya zipten)</li>
	<li>Java binary dosyalarinin PATH'e ekli oldugundan emin olun. (Ortam degiskenleri)</li>
	<li>Eclipse'i calistirilir.</li>
	<li>Arkasindan Qt pluginini zipten ya da tardan cikartilir. Eclipse'in plugin ve feature klasorunun altina cikartilan dosyalar atilir(plugin ve feature diye iki klasor çıkıyor zaten merge et gitsin). Eger isteniyorsa dokumantasyon da ayni sekilde atilir. Eger windowsta yukleme yapiliyorsa indirilen plugin dogrudan setup wizard yardimiyla kurulabilir. Ama dokumantasyon icin mecburen plugin klasorune kopyalama isleminin yapilmasi gerekir.</li>
	<li>Eclipse yeniden baslatilir.</li>
	<li>Eger basarili olunmussa eclipse'in acilisinda Qt eklentisi ilk defa calisiyor diye bir uyari cikar.</li>
	<li>Eclipse menulerinden Window/Preferences/Qt gidilir ve Qt'nin yuklu oldugu klasorun yolu gosterilir.</li>
	<li>Thats it!</li>
</ul>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/11/screenshot-qt-c-media-local-disk-projects-c-ubuntu_cpp_ws-qtdene1-qtdene1-ui-eclipse.png">
<img class="aligncenter" src="http://devdala.files.wordpress.com/2011/11/screenshot-qt-c-media-local-disk-projects-c-ubuntu_cpp_ws-qtdene1-qtdene1-ui-eclipse.png" alt="" width="614" height="344" /></a><a href="http://devdala.files.wordpress.com/2011/11/untitled-picture.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/11/untitled-picture.png" alt="" width="589" height="354" /></a></p>
<p style="text-align: center;"></p>