---
layout: post
title: Wordpress ile Facebook yorumu entegrasyonu
date: '2012-02-18 12:08:01'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2012/02/inf-tdk-mkv_20120107_234336-551.jpg"><img class="aligncenter" title="Lusiyis" src="http://devdala.files.wordpress.com/2012/02/inf-tdk-mkv_20120107_234336-551.jpg" alt="" width="725" height="300" /></a></p>
9gagdeki gibi hani altta feysbukta halihazirda login olmus insanlar hemen girip yorum yazsinlar istemez misin. Nasil mi cok kolay. Kendi sorusunu cevaplayan ogretmen gibi oldum. Denedim %100 calisiyor.

Birkac baska yontem olsa da piyasada, ben pluginsiz temiz, hizli ve basit bir yontem kullaniyorum. Basitlik guzel malum.
<ol>
	<li>Su adrese gidilir oncelikle : <a href="https://developers.facebook.com/apps" target="_blank">Facebook developer app</a></li>
	<li>Izin isterse verilir. E verin yani. Ondan sonra sagdan "yeni uygulama olustur" denir.</li>
	<li>"App Display Name"ine duzgun bisiler yazilir. Namespace simdilik bos birakilsa da olur. Amac bi app id elde etmek.</li>
	<li>Continue dendikten sonra bir app id bir de security pass verir feysbuk. Bunlari ezberlemeye gerek yok. Adamlar yapmis. Kodu direk aldi mi icinde geliyor.</li>
	<li><a title="Official facebook comment plugin" href="http://developers.facebook.com/docs/reference/plugins/comments/" target="_blank">Official Facebook Comment Plugin</a> bu adrese gidilir.</li>
	<li>Alttaki fotodaki kisima gelip gerekli ayarlar yapilir. Hani cok da onemli degil. Kodu aldiktan sonra manuel olarak editlenebiliyor kendileri zaten. Ama tabi pa$a gonul bilir.<a href="http://devdala.files.wordpress.com/2012/02/facebookcomment1.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/02/facebookcomment1.png" alt="" width="248" height="313" /></a></li>
	<li>"Get code"a basinca 2 tane kisim cikar. ustteki wordpress blogundaki <strong>header.php</strong> nin body kisminin icine yapistirilir. Bu onemli bu ilerki safhalar icinde gerekli. Mesela like on facebook ya da send via facebook butonlari eklemek icin de headerda bu kodun olmasi gerekir.</li>
	<li>Alt taraftaki wordpress blogunun <strong>comments.php</strong> dosyasinin istenilen yerine yapistirilir. Tabi su sekilde: (linki degistirmeyi unutmayalim)</li>
</ol>
<blockquote>
<pre>&lt;div data-href="&lt;?php the_permalink(); ?&gt;" data-num-posts="2" data-width="470"&gt;&lt;/div&gt;</pre>
</blockquote>
<ol>
	<li>Ben uste yapistirdim. Boylece facebook yorum kutusu normal yorum kutusunun ustunde cikiyor. Isterseniz alttaki kutuyu toptan silip(ki bu sonra aksiliklere yol acarsa bana bagirmayin ben silmedim) sadece facebook yorumlari birakilabilir. En olmadi &lt;!-- yorum satiri --&gt; yapilip bakilabilir eger isteniyorsa. Alternatif iyidir.</li>
</ol>
Yorumlari eksik etmeyelim:D