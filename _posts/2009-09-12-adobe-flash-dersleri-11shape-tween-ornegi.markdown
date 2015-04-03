---
layout: post
title: Adobe Flash Dersleri 11(Shape tween örneği)
date: '2009-09-12 12:41:20'
---

<div><span style="font-family:Calibri;font-size:medium;"><span>Perde kapanması veya kan akması gibi animasyonlarda kullanılabilecek bir sistemdir. </span></span></div>
<div><span style="font-family:Calibri;font-size:medium;"><strong>
</strong></span></div>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>ActionScript 2.0 açılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>2 katmana ihtiyaç vardır.      1.si siyah zemin için 2.si yukarıdan akacak kan için</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Siyah olacak katmanın arka      plan rengi "Properties"den siyah yapılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yazı yazılmak istenirse yazılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Siyah zeminin kan      animasyonunu sonuna kadar etmesi istendiği için 150. kareye gelinip buraya      "Insert Keyframe" yapılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Kan katmanına gelinir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Sahnenin üstüne "Pen      tool" ile bir şekil çizilir ki bu ileride kan olacaktır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>İçi kırmızı renk ile      doldurulur</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Eğer nesne "Shape"      değil de "Drawing Object" ise nesne seçilip sağ tıklanıp      "Break apart" denir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>1inci kareye gelip sağ tıklanır      ve "Create Shape Tween basılır"</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>10uncu kareye gelinip      "Insert Keyframe"e basılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Artık nesnenin alt kısmına      gelince fare imlecinin şeklinin altında bir yay görünecektir. Bu yay ile      nesneyi aşağı doğru yuvarlayarak sahneye yavaş yavaş girmesi sağlanır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Aynı şekilde 15. kareye      gelinip "Insert Keyframe" yapılıp sahnenin boş yerine tıklanırsa      yine imlecin altında yay belirir ve yine biz kan şeklini sahneye biraz      daha yuvarlatarak sokarız</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Bu şekilde ekranın tamamı      kaplanana kadar devam edilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Eğer zeminin bittiği kare      daha ilerideyse(150 yapmıştık yukarıda) aradaki fazlalık kareler seçilip      "Remove Frames" yapılarak silinir.</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Ctrl+enter</strong></span></li>
</ol>