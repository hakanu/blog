---
layout: post
title: Google Docs vieweri kullanarak siteye döküman gömmek
date: '2012-01-20 23:05:31'
---

Sayfalara pdf, doc, ppt eklemek icin birkac yontemvar. Scribd bu yontemlerden biri. Google Docs bir baska yol. Google Docs'un viewer biraz daha hizli ve esnek gibime geliyor. Ayrica dokumaninizi scribd uzerinde yayinlamaniza da gerek kalmiyor. Tabi tercih meselesi bu.

Viewer'a surdan erisilebilir:

<a href="https://docs.google.com/viewer">https://docs.google.com/viewer</a>
<ul>
	<li>Oncelikle pdf belgesini nette bi yerlere yuklemek lazim. Ben bunun icin depo olarak kullandigim wordpress uzantili blogumun alanini kullandim. Dosyayi yukledigimde soyle bir baglantisi oluyor:</li>
</ul>
<code>
http://devdala.files.wordpress.com/2012/01/dosyaIsmi.pdf
</code>
<ul>
	<li>Bu url i tutup ustteki google docs viewer'dan gerekli embed kodunu urettiriyoruz. Suna benzer bir sey oluyor o da:</li>
</ul>
&nbsp;

<code>
<pre lang="html4strict">
<iframe style="border: none;" src="http://docs.google.com/viewer?url=http%3A%2F%2Fdevdala.files.wordpress.com%2F2012%2F01%2FdosyaIsmi.pdf&amp;embedded=true" width="600" height="780">
</iframe>
</pre>
</code>

&nbsp;
<ul>
	<li>Bunu iframe istenilen yere yapistirilabilir. Wordpress editorunde html'den yapistirmayi unutmayin. Eklentiye falan gerek yok. Bi de bazen chrome'da gozukmeyebiliyor. Firefox'ta bakilmasina.</li>
</ul>