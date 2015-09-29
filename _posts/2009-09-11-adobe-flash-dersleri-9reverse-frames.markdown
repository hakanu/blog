---
layout: post
title: Adobe Flash Dersleri 9(Reverse Frames)
date: '2009-09-11 23:08:02'
---

<div>
<div>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><strong>Yapılan bir animasyonu tersine çevirmek için kullanılır. Oyun programlama sırasında da çokça kullanılan bir metottur. Çarpmalardan sonra hızı eksi ile çarpılıp nesne geri yollanır.</strong></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><strong>Örnek olarak gölgesi olan zıplayan top yapılacaktır.</strong></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>

</div>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>ActionScript 2.0 açılır</strong></span></span></li>
</ol>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Bir top bir de gölge katmanı(layer)      oluşturulur</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Gölge katmanına Oval tool ile      gri bir gölge oluşturulur.</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Top katmanına Oval tool ile      bir top çizilir</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Top için bir motion tween oluşturulur</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Gölge için de oluşturulur</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>1inci karede top üstte iken      20. karede gölgenin üstündedir</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Şu anda animasyon önceki      derslerdeki gibidir. Bizim amacımız top gölgenin üstüne geldikten sonra      geri yansımasını sağlamaktır. </strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Top katmanında 20. kareden başlanarak      1. kareye kadar olan kareler seçilip(20. kareye tıklanıp shift tuşuna basılı      tutarken 1. kareye basılarak da seçme yapılabilir) sağ tıklanır ve      "Copy frames"e basılır</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>21inci kareye gelinir</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>"Paste frames"e basılır</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>40ıncı kareden 21. kareye      kadar olan kareler seçilip sağ tıklanır</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>"Reverse Frames"e      basılır</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Tween tersine çevrilmiş olur.      Top yukarı çıkar bu kez</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>Gölge için de aynısı yapılır</strong></span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;"><span style="color:#000000;"><strong>İstenirse aşağıdan yukarı çıkma      yavaşlatılabilir.(Tween üzerindeki herhangi bir kareye tıklanıp properties      menüsünden "Ease" değeri düşürülerek)</strong></span></span></li>
</ol>
</div>
<ol><span style="color:#000000;"><strong> </strong></span></ol>