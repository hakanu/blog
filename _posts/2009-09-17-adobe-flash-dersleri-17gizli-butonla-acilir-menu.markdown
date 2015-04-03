---
layout: post
title: Adobe Flash Dersleri 17(Gizli butonla açılır menü)
date: '2009-09-17 11:32:23'
---

<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>Butonun üstüne gelince alt menü oluşmasını sağlamak için bir yöntemdir</strong></span></p>

<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>
</strong></span>
<ol style="margin-left:.3902in;direction:ltr;unicode-bidi:embed;margin-top:&amp;margin-bottom:0;font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>ActionScript 2.0 açılır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>İlk katmanda bulunan butonun      sürekli görünmesi istendiğinden(gizli buton olacaktır bu çünkü) ilk 70-80      kareye "Insert Keyframe" yapılır. Bu keyfi bir değerdir. Az      gelirse daha ileriki framelere "Insert Keyframe" yapılabilir. Kısaysa      da daha önceki karelere "Insert Keyframe" yapılabilir</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Bir tane buton oluşturulur</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Bir katman oluşturulup bu      katmana ilk yapılan butonun altına bir tane daha buton oluşturulur</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Alt a oluşturulan butonun      olduğu katmana gelinip 1. kareye "Create Classic Tween" yapılır      ve 10. kareye "Insert Keyframe" yapılır. 1. karede önce sahneye      sonra butonun üstüne tıklanıp "Properties" panelinden      "Alpha" değeri 0 yapılır. Böylece buton yavaş yavaş ekranda      belirecektir. Bir katman daha açılır ve 10. karesine "Insert      Keyframe" yapılır. Böylece 1. alt buton animasyonu görünürken az      sonra oluşturulacak olan 2. buton ekranda görünmez</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Buraya(2. açılan katmanın 10.      karesine) bir buton daha oluşturulur</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Bu butona da tween eklenir.      10. kareye "Create Classic Tween" yapılır. 20. kareye      "Insert keyframe" yapılır. Ardından bu katmandaki 20. kareye tıklanıp      stop(); yazılır. Böylece açılır menü açıldığında kaybolmaz hemen. Çünkü aşağıda      kaybolma efekti de görünme efektinin arkasına yapılacaktır. Açılır menü      ana butonun üstünden fare imleci çekilmediği sürece açık kalmalıdır. Bu      istendiği için kaybolma efektine gelmeden animasyon durdurulur.</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Önceki katmanda da 20. kareye      "Insert keyframe" yapılır. Böylece önceki katmandaki buton ana      butonun altında belirecek, tamamen belirince de diğer buton belirecektir</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Bu işlemden sonra sırayla      ekrandan kaybolma işlemi yapılacaktır. Bunun için önce son belirenin      ekrandan çıkması sağlanmalıdır. Bu nedenle son eklenen katmana gelinip 30.      kareye "Insert keyframe" yapılır. 30. karede önce sahneye sonra      butona basılıp "Properties" panelinden "Color effect"e      gelinip "Alpha" değeri 0 yapılır. Böylece 20. ve 30. kareler      arasında buton ekrandan kaybolacaktır. </strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Alttaki buton kaybolurken      üstteki butonda bir değişiklik olması istenmediğinden onun katmanında da      30. kareye "Insert keyframe" yapılır ve efekt eklenmeyip olduğu      gibi bırakılır. Animasyon oynatıldığında ekranda önce sürekli durması      gereken ana buton görünür ve yavaşça onun altında bir buton belirir. Ardından      bir buton daha belirir. Sonra son beliren, en alttaki buton yavaşça      ekrandan kaybolur. İlk beliren buton aynen kalır.</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>İlk beliren butonu da      ekrandan yavaşça kaybetmek için 40. kareye "Insert keyframe" yapılır      ve önce sahneye sonra butona tıklanıp "Properties" panelinden      "Color effect"e gelinip "Alpha" değeri 0 yapılır.      Böylece artık bu buton da kaybolacaktır. </strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Şu an için görünme ve      kaybolma efektleri tamamlanmıştır. Sıra ana butona kod ekleyerek diğer iki      alt butonu yönlendirmeye gelmiştir. Ancak bundan önce animasyonun otomatik      olarak oynamasını engellemek için ana butonun olduğu katmandaki 1. kareye      tıklayıp "Actions-Frame" panelinden stop(); yazılır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Önce sahneye sonra ana butona      tıklayıp "Actions-Button" panelinden ana butona kod yazılmaya başlanır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>on(rollOver){</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;"><strong>gotoAndPlay(2);</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>}</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>**1. karede stop();  kodu olduğu için bu kodla o aşılır ve animasyonun oynamaya başlanması sağlanır</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Yeni bir katman oluşturulur.      Buraya gizli buton yapılacaktır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>20nci kareye gelip      "Insert keyframe" yapılır. Çünkü görünme efektlerinin sonu 20.      karedir. Timeline'da görülen fazlalık kareler seçilip sağ tıklanıp      "Remove frames" ile silinebilir</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Rectangle tool ile 20. kareye      gelip görünen 3 butonun etrafını tamamen saracak bir şekil çizilir.      Dikdörtgenler üst üste çizilirse Flash onları tek şekil olarak algılayıp işimizi      kolaylaştırır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Şekil çizildikten sonra şekle      tıklayıp F8 veya "Convert to Symbol"e basılarak şekil, butona      çevrilir</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Butonun üzerine çift tıklanıp      içine girilir ve Up, Over, Down, Hit gibi alanlar görünür</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Önceki derslerin aksine bize      gereken sadece Hit alanıdır. Çünkü gizli butonun üstüne gelince açılır      menünün kaybolmasını istiyoruz. (Yani fare imleci ana butonun üzerinden      çekilince mecburen az önce yaptığımız gizli butonun üzerinden geçecektir).      Bunun için timelinedaki "Up" alanındaki noktaya tıklanıp      "hit" alanına sürüklenir. Tekrar Scene1'e dönüldüğünde gizli      butonun rengi değişir ve animasyonda görünmez</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Önce sahneye sonra gizli      butona tıklanıp "Actions-Button" panelinden butona kod yazılır</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>on(rollOver){</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><span style="color:#000000;"><strong>play();</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>}</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong>**20. karede  yazılan stop() ; kodunu geçip kaybolma efektini oynatmak içindir</strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Artık ana butonun veya alt      menünün dışında bir yere fare imleci sürüklenirse alt menü kaybolacaktır. </strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><span style="color:#000000;"><strong>Ctrl+enter</strong></span></span></li>
<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>

<span style="color:#000000;"><strong> </strong></span></ol>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:#000000;"><strong> </strong></span></p>