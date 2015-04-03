---
layout: post
title: Adobe Flash Dersleri 13(gotoAndPlay kullanımı)
date: '2009-09-12 14:27:50'
---

<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">Ekranda hiçbir hareket yokken butona basıldığında ekranda animasyonun oynamasını sağlamak için kullanılabilecek bir yöntemdir</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;font-weight:bold;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-family:Calibri;font-size:11pt;font-weight:bold;">ActionScript      2.0 açılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">İlk katman animasyon katmanı olacak. Bu katmanda ilk 20 kare boş bırakılır.(20.      kareye "Insert Keyframe" yapılır)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">20nci kareye bir top çizilip "Create Classic Tween"e basılarak      bir motion tween oluşturulur</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">40ıncı kareye "Insert keyframe" yapılır ve topun 40.      karede bulunacağı yer belirlenir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Başta hareket etmesini istenmediği için 1. kareye stop kodu      koyarak hareketi engellemek gerekir.</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">1inci kare seçilip "Actions" panelinden kod sayfası açılıp </span><span style="font-weight:bold;font-style:italic;font-family:Calibri;font-size:11pt;">stop();</span><span style="font-weight:bold;font-family:Calibri;font-size:11pt;"> yazılır. Artık animasyon hiç başlamayacaktır.</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Yeni bir katman oluşturulur. Bu buton katmanı olacaktır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Buton çizilir. Yazısı yazılır. Zemin ve yazı seçilip F8 ile      "Convert to Symbol" ile "Button"a çevrilir. Bu butona      1. kareyi atlayıp direk 20. kareden animasyonu başlatıcı görevi yapacaktır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Önce sahneye sonra butona tıklanıp "Actions" panelinden      butonun içine kod yazma ekranı açılır</span></li>
</ol>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">on(release){</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">gotoAndPlay(20);</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">}</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">Bu kodun manası "20. kareye git ve oynat"tır</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">Aynı uygulamayı movie clip için yapmak için ise:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;"></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;font-weight:bold;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-family:Calibri;font-size:11pt;font-weight:bold;">ActionScript      2.0 açılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Rectangle tool ile sahneye bir alan çizilir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">F8 tuşu ile veya "Convert to Symbol" ile bu alan      "movie clip"e çevrilir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Nesne seçilip "Properties" panelinden "Instance      Name"e istenilen ad verilir(kesin yapılmalıdır)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Movie clipe çift tıklanarak içine girilir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">İçindeki katmana bir tane top çizilir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">1inci karede "Create Classic Tween" yapılır ve 20.      karede "Insert Keyframe" yapılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Tekrar Scene1'e gelinir.(Movie Clip'in dışına çıkılır)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;color:black;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Önceki derslerdeki gibi 2 tane buton oluşturulur.(Oynat ve      durdur.)</span></li>
</ol>
<p style="font-weight:bold;text-decoration:underline;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">Oynat butonu kodu:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">on(release){</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">_root.tur.play();</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">}</p>
<p style="font-weight:bold;text-decoration:underline;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">Durdur butonu kodu:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">on(release){</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">_root.tur.stop();</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;color:black;margin:0 0 0 .375in;">}</p>