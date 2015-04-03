---
layout: post
title: Wordpress'e Facebook like butonu, tweet butonu ve +1 butonu eklemek
date: '2012-02-18 12:23:30'
---

<a href="http://devdala.files.wordpress.com/2012/02/fritz-lang-m-1931-dvdrip-sirius-share-cd2-avi_20110910_022328-030.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/02/fritz-lang-m-1931-dvdrip-sirius-share-cd2-avi_20110910_022328-030.jpg" alt="" width="512" height="432" /></a>

Fazlaliklari atiyorum. Wordpress'e daha fazla eklenti kurmaca yok artik. En azindan boyle basit islemler icin.

Oncelikle sunu soylemeliyim ki bu benim yabanci kaynaklardan faydalanarak kendi uydurdugum bi metod. Zaten bapbasit.

First thing is first. Butonlarin nereye konmak istedigine karar verilir. Ben yorumlarin ustune koydum mesela. Aliskanlik geregi. Ama postun tepesine koyanlar da var. Benim yolum icin wordpress editor'den comments.php acilir.

Icine yeni bir div blogu eklenir su sekilde:
<blockquote>
<pre>&lt;div&gt; &lt;!--eklenecek kodlar buraya--&gt; &lt;/div&gt;</pre>
</blockquote>
<ul>
	<li>Facebook begen(like) ve gonder butonu icin asagidaki adrese gidilir. Tabi bundan once developer uygulamasinin profile erisimine izin verilmelidir.</li>
</ul>
<a href="http://developers.facebook.com/docs/reference/plugins/like/" target="_blank">http://developers.facebook.com/docs/reference/plugins/like/</a>

Oradaki widgettan stil ayarlarini yaptiktan sonra "get code" denir. 2 parca halinde kod gorunur. Usttekinin nereye yapistirilacagi ile ilgili yazi surda: <a href="http://www.hakanu.net/?p=2093" target="_blank">Wordpress ile Facebook yorumu entegrasyonu</a> 7. adiminda gecen olaya dikkat.

Ben kisaca geceyim ustunden. Ustteki kod header.php'te body taginin altina yapistirilir.Tamam simdi 2. kod parcasini yani asil arayuzde gorunecek butonlari koyma zamani. comments.php'ye gidilir. Orda daha once yukarda acilan div taglerinin arasina facebook developer sayfasindan alinan 2. kod parcasi yapistirilir. Sayfa kaydedilip son duruma bakilabilir. Brova! Pluginsiz facebook like ve send butonlari bloga eklenmis oldu. Facebook isimleriyle yorum nasil yazdiririm diyenler bu tarafa gitti: <a href="http://www.hakanu.net/?p=2093" target="_blank">Wordpress ile Facebook yorumu entegrasyonu</a>
<ul>
	<li>Twitter 'da paylas ki bu en kolay ve en sevdigim. Su adrese gidilir: <a href="https://twitter.com/about/resources/buttons" target="_blank">https://twitter.com/about/resources/buttons</a></li>
</ul>
Istenen buton secilir. Burda birkac cesit buton var (Tweet, floow, hashtag, mention etc).

Secilen butonun embed kodu sagda cikar kutunun icinde hrefli falan. O kopyalanip yine az onceki gibi wordpress'te acilan comments.php'de bulunan div taginin icine yapistirilir.
<ul>
	<li>+1 butonu en kolayi sanirim. Google diye demiyorum basit yapiyorlar :-O</li>
</ul>
Su adrese gidilir: <a href="http://www.google.com/webmasters/+1/button/" target="_blank">http://www.google.com/webmasters/+1/button/</a>

Kod direk kopyalanip comments.php'de az once acilan div taginin icine atilir.

Bu kadar. comments.php'yi kaydetmenin unutulmamasina.

Repleri esirgemeyelim.