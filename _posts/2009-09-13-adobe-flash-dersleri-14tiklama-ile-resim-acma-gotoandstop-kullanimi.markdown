---
layout: post
title: Adobe Flash Dersleri 14(Tıklama ile resim açma-gotoAndStop kullanımı)
date: '2009-09-13 22:51:53'
---

<p style="font-weight:bold;font-size:11pt;margin:0;"><span style="color:#000000;">Butona tıklandığında resmin açılmasını sağlamak için kullanılan yöntemdir</span></p>

<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;font-weight:bold;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-size:11pt;font-weight:bold;"><span style="color:#000000;">ActionScript 2.0 açılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Her resim      için bir katman kullanacağız</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">1inci resmin      katmanında 10. kareye "Insert Keyframe" yapılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">İlk resim      sahneye import edilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Yeni bir      katman açılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Bunda da 15.      kareye "Insert Keyframe" yapılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Resim 15.      kareye import edilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Yeni bir      katman açılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Bunda da 20.      kareye "Insert Keyframe" yapılır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Resim 20.      kareye import edilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Şu an      resimler slayt gösterisi şeklinde otomatik olarak hareket eder ki      ctrl+enter yapıldığında bu görülebilir</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Bunu kontrol      altına almak için 1. katmanın 1. karesine gelinip      "Actions-Frame" panelinden kod kısmına stop(); yazılır. Böylece      artık slayt gösterisi yerine sadece ilk resim ekranda görünür</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Yeni bir      katman oluşturulur. Buraya butonlar yapılacaktır</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Butonlar oluşturulur</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">3 resim için      3 ayrı buton oluşturulur(önceki derslerde yapımı ayrıntılı anlatılmıştı)</span></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-weight:bold;font-size:11pt;"><span style="color:#000000;">Butonlar oluşturulduktan      sonra her birine kod yazılır. Önce sahneye sonra butona bir kez tıklanıp      "Actions" panelinden kod kısmı açılır. Yazılacak kodlar şu şekildedir:</span></span></li>
</ol>
<p style="font-weight:bold;text-decoration:underline;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">1.buton için:</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(release){</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">gotoAndStop(10);</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>
<p style="font-weight:bold;text-decoration:underline;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">2.buton için:</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(release){</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">gotoAndStop(15);</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>
<p style="font-weight:bold;text-decoration:underline;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">3.buton için:</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">on(release){</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">gotoAndStop(20);</span></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">}</span></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"></p>
<p style="font-weight:bold;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;">gotoAndStop kodunun manası, içinde yollanan parametredeki kareye git orda durdur.</span></p>