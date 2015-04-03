---
layout: post
title: Adobe Flash Dersleri 15(Reklam banneri yapma)
date: '2009-09-15 15:44:28'
---

<div><span style="font-family:Calibri;"><span style="font-size:medium;"><strong>Web sitelerinde bulunan reklam veya tanıtım amaçlı bannerların yapımında kullanılan tekniktir.</strong></span></span></div>
<ol>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">ActionScript 2.0 açılır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Öncelikle sahnenin      "Properties" panelinden reklamın boyutları ayarlanır. Çünkü      sitelerde bunlara sınırlı bir alan verilir</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">İstenilen resimlerin hepsi      library'ye aktarılır. (File- Import - Import to library)</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Resimler sahnede bulunmamalı.      Önce libraryde bekletip sonra sahneye alınacaktır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Her resim için bir katman oluşturulur</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">İlk katmana ilk resim konur</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Bu resme bir motion tween      eklenir(Resmin olduğu katmanın ilk karesine "Create Classic      Tween" ve sonlanmasını istediğimiz kareye-mesela 20.kare-      "Insert Keyframe" yapılır)</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">İlk resmin olduğu katmanda 1.      kareye gelinip önce sahneye sonra resme tıklanıp "Properties"den      "Color"(veya "Color effect" versiyona göre değişebilir)      kısmındaki "Alpha" değeri 0 yapılır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;"> Resimlerin sırayla görünmesi istendiğinden      ilk 20 karede 1. resim görünecektir. 2. resim 20. kareden sonra görünmeye      başlayacaktır. Bu nedenle 2. resmin katmanında 20. kareye "Insert      Keyframe" yaparak boş kalması sağlanır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">20nci kareye 2. resim konur      ve bu resme de ilk resme uygulanan tweenden uygulanır. (Örneğin 20. kareye      "Create Classic Tween" basıp 40. kareye "Insert      Keyframe" yapılır)</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">2nci resme yukarıdaki gibi      "Alpha" efekti eklenir</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">3üncü resim 3. katmana      eklenir</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">İlk 40 karede görünmemesi      istendiği için 40. kareye "Insert Keyframe" yapılır. </span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">40ıncı kareye "Create      Classic Tween" yapılıp 60. kareye "Insert Keyframe" yapılarak      3. resme de efekt eklenir</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Resme tıklanıp      "Properties" panelinden "Alpha" efekti verilir</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Ctrl+Enter yapıldığında bir      eksik olduğu görülür. 2. resim çıkarken 1. resim kaybolur. 3. çıkarken 2.      kaybolur. Bunu engellemek için 1. resmin katmanında 60. kareye      "Insert Keyframe" yapılır ve 2. resmin katmanında da bu uygulanır.      Çünkü 60. kare animasyonun son karesidir. Tweenler bitince resimlerin      hiçbir şey yapmadan görünmesi istendiği için böyle yapılır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Banner biraz daha hoş bir      hale getirmek için her katmanın sırayla bütün kareleri seçilir(Benim örneğimde      ilk 60 kare)</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Seçilen karelerin üstüne sağ      tıklanıp "Copy frames" yapılır</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Her katmanın son karesinde      bir sonraki kareye sağ tıklanıp "Paste frames" yapılır.(Bende      61. frame)</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Şu anda yapılan sadece aynı şeyi      iki kere oynatmak oldu. Henüz bitmedi. Sonradan yapıştırılan kareler      seçilip sağ tıklanır ve "Reverse Frames" yapılır. Bu her katman      için uygulanır. Böylece hoş bir görünme ve kaybolma efekti sağlanır.</span></strong></li>
	<li><strong><span style="font-family:Calibri;font-size:11pt;">Ctrl+enter</span></strong></li>
</ol>
<ol style="margin-left:.3902in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;">
<p style="font-family:Calibri;font-size:11pt;margin:0;"><strong>
</strong></ol>