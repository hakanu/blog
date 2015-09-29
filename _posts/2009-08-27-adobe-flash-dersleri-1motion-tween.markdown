---
layout: post
title: Adobe Flash Dersleri 1(Motion Tween)
date: '2009-08-27 21:20:33'
---

<span style="font-family:arial black,avant garde;color:#000000;">Motion tween'i şu an için Flash programı ile küçük hareketler oluşturmak için kullanacağız. Ben Adobe Flash CS4 kullanıyorum. Genel olarak arayüzde birkaç küçük değişiklik dışında içerik aynıdır her Flash versiyonu için. İlk Motion Tweenimizi oluşturalım</span><span style="color:#000000;"> </span>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Birinci Frame'i seçilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Bir nesne oluşturulur</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Nesne seçilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Birinci frame'e sağ tıklanır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Create classic motion tween'e basılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;"><span> </span>Kacıncı frame'i istiyosan seç sağ tıklanır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Insert keyframe basılır</span></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Buton yapma ve kod ekleme</span></span></p>

<ol style="margin-left:.3902in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Yeni bir layer oluşturulur</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Rectangle toolla falan bi      buton yapılır yazısını yazılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Buton seçilir tümden</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Modify menüsünden convert to      symbol yapılır(F8)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Button yapılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Butonu seçilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Window menüsünden Actions      basılır(F9)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Kod penceresi cıkacak</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Butona kod yazmak için önce      sahneye sonra butona tıklamak lazım</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Kod kısmı:</span></span></li>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">on(release){</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Play();</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">}</span></p>

	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Yukardaki kod motion      tweenimizi oynatır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Check işaretine basıp kodu      syntax olarak onaylasın</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Autoformat diyince kodların      girintisi cıkıntısını ayarlar</span></span></li>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">
</span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">***Butonun motion'i  durdurmasını istersek:</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">on(release){</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Stop();</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;">}</span></p>
</ol>