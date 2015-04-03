---
layout: post
title: Adobe Flash Dersleri 12(İleri-geri butonlu albüm yapmak)
date: '2009-09-12 13:21:47'
---

<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">Web sitelerinde de kullanılabilecek veya interaktif tanıtım cd leri için işe yarayacak bir yöntemdir</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;font-weight:bold;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;font-weight:bold;">Actionscript 2.0 açılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Bir tane      resim katmanı gerekir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Resimlerin      boyutuna göre Flash sayfası "Properties"den boyutlandırılır.(640x480      mesela)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Resimler      sahneye eklenir. Hepsi seçilip eklenir.(File - Import - Import Stage basılıp      istenen resimler çoklu seçilip projeye dahil edilir. Kütüphanede eklenen      resimler görülebilir)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">1inci kareye      1. resim koyulur</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">2nci kareye      gelinip "Insert Keyframe" yapılır v resmin üstüne tıklanır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Resmin      özellikleri olan "Properties"den "Swap" butonuna basılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Çıkan      listede 2. sıradaki resim seçilir</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Bu işlem      istenilen sayıdaki resim için tekrar tekrar yapılır ve sonuçta Ctrl+enter      yapıldığında resimlerin slayt gösterisi halinde geçtiği görülür</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Yeni bir      katman açılır. Bu katman kod yazmak için kullanılacaktır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">1inci kare      seçilip "Actions"tan içine</span><span style="font-weight:bold;font-style:italic;font-family:Calibri;font-size:11pt;"> stop();</span><span style="font-weight:bold;font-family:Calibri;font-size:11pt;"> yazılır</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Artık sadece      ilk resim gösterilir ve slayt devam etmez</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Butonlar yapılır.      (İleri ve geri olmak üzere önce rectangle tool ile şekilleri çizilip içine      yazıları yazılır. Zemin ve yazı seçilip her bir rectangle "Convert to      Symbol"e basılarak veya F8 kısayolu ile "Button"a      çevrilir.)</span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-family:Calibri;font-size:11pt;">Butonların      içine kodları yazılır. Buton seçilip "Actions"a basılır.</span></li>
</ol>
<p style="font-weight:bold;text-decoration:underline;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;text-decoration:underline;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">İleri butonu kodu:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">on(release){</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">nextFrame();</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">}</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;text-decoration:underline;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">Geri butonu kodu:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">on(release){</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">prevFrame();</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;">}</p>