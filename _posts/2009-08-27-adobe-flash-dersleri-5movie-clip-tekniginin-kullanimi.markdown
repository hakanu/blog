---
layout: post
title: Adobe Flash Dersleri 5(Movie Clip tekniğinin kullanımı)
date: '2009-08-27 21:24:21'
---

<p style="font-family:Calibri;font-size:17pt;color:red;margin:0;">Movie Clip Tekniği</p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">ActionScript 2.0 açılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">1inci frame'e animasyonun ilk      karesini çizilir(top mesela)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Nesnenin üstünde sağ tıklayıp      "Convert to symbol"e basılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Kod kısmında karışıklık yaşamamak      için isim verebiliriz(top mesela)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Ardından bu nesneyi      "Movie Clip" haline getirip OK denir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Nesnenin ortasında bir artı işareti      belirir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Daha sonra "Properties" kısmından "Instance Name" belirtilir(Kesin yapılmalı. Top_mc yaptım ben mc movie clip manasında ileride yararı olacak)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Movie Clip'in ortasındaki artı      işaretine basılarak içine girilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Animasyon burada oluşturulur</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">1inci frame'e sağ tıklayıp      "Create Classic Tween"e basılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">20inci frame'e gelinip sağ tıklanıp      "Insert Keyframe"e basılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">20inci frame'de 1inci      framedeki nesnenin nerede olacağı belirlenir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Timeline'dan Scene 1'e bakıldığında      sadece top varken içine girildiğinde bir tween vardır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Buna iki tane buton      ekleyelim(Stop ve Play)**alt tuşuna basıp nesneyi yana çekince kopyalama      yapılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Burada yazılacak kodlar değişiklik      gösterir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Stop butonunu ele alalım: Sahne      1'de bulunan topu durdurmak istediğimiz için</span></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(release){</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">_root.top_mc.stop();</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="color:#000000;"><span style="font-family:Calibri;font-size:11pt;">Aynı şekilde play butonu için:</span></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(release){</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">_root.top_mc.play();</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Burada kullanılan _root Scene 1'i simgeler. Yani ilk yaptığımız sahnedir.</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">(release) yerine (rollOver) kullanılırsa butona basılmadan üstüne gelindiğinde içine yazılan kod işler</span></p>

<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">
</span>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">Not: Projede yapılan herşey Library sekmesinde görünür.(top, butonlar…vb)</span></p>