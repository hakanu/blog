---
layout: post
title: Adobe Flash Dersleri 3(Motion Guide ile nesneyi belli yörüngede hareket ettirme)
date: '2009-08-27 21:22:47'
---

<p style="font-family:Calibri;font-size:17pt;margin:0;"><span style="color:#ff0000;">Motion Guide
</span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">Nesneye motion guide ekleyerek onun belli bir yol boyunca ilerlemesini sağlamak</span></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">ActionScript 2.0 projesi yarat</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Layer'a isim ver karışmasın</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">1inci frame e bir nesne      çiz(daire falan)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Çizilen nesne Graphic olmalıdır. </span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Modify - Convert to Symbol'e      gir bak. Eğer Graphic seçili değilse seç</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">1inci frame'e sağ tıkla      "CreateClassic<span> </span>Motion      Tween" bas</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">25inci frame'e gelip "Insert      keyframe" bas </span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">25inci frame'de topu      gitmesini istediğin yere koy. </span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">İlk dersteki motion tween'in      aynısı oldu</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Timeline'in sol alt köşesindeki      "Add motion guide" bas(cs3 için)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">CS4 içinse layer'a sağ tıklayıp      "Add Classic motion guide" bas</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Sonra ekrana istediğin bir şekil      çiz</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">İlk başta motion tween yapılan      nesne bu guide şeklinin üstüne oturur</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Ctrl+enter</span></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;"> </span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Not: İstenirse 1. derste anlatılan yöntemle nesnelerin hareketi butonlarla kontrol edilebilir. </span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Butona tıklamadan sadece üstüne gelindiğinde yazılan action çalışsın istenirse kod şöyle olmalıdır:</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;"> </span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(rollOver){</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;"> play();</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>