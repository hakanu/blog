---
layout: post
title: Adobe Flash Dersleri 10(Resimli Buton yapımı)
date: '2009-09-12 00:20:33'
---

<p style="font-family:Calibri;font-size:11pt;margin:0;"><strong>Üstüne gelindiğinde şekil değiştiren buton yapımı. (Bazı sitelerdeki reklam bannerları tarzında)</strong></p>

<p style="font-family:Calibri;font-size:11pt;margin:0;"><strong>
</strong>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0 0 0 .375in;"><strong>Buton sabit, resim hareketli:</strong></p>

<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><strong>
</strong>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>ActionScript 2.0 açılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Rectangle tool ile bir buton      çizilir.(Çizme işlemini tamamlamadan yani eli rectangle tool ile çizilen      dikdörtgenin köşesinden kaldırmadan klavyenin yukarı - aşağı tuşlarıyla      butona değişik şekiller verilebilir)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Butona yazı yazılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Hepsini seçip önceki      derslerde olduğu gibi çizilen nesne ve yazı butona çevrilir(F8 kısayol)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Butonun üzerine çift tıklanarak      içine girilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Up-Over-Down-Hit alanları      görülür. Up butonun normal hali, over fare üstündeyken bulunduğu hali,      down basılı olduğundaki hali, hit ise farenin üzerinde bulunduğu alandır.</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Sadece Up aktiftir başta. Diğerlerini      de aktifleştirmek için Up seçili iken F6 tuşuna basılır ve diğerleri de      doldurulur</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Fare ile üzerine gelince      resim açılması istendiğinden Over üzerinde çalışmak gerekir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yapılan buton tamamen seçilip      Over alanındayken F8 tuşuyla buton, movie clip haline getirilir.</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Nesnenin ortasındaki yuvarlağa      çift tıklanarak movie clipin içine girilir. Karşımıza ilk proje oluşturduğumuzda      çıkan ekrana benzeyen bir timeline çıkar</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yeni bir katman oluşturulur.      Bu katman resim içindir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Butonda gösterilmek istenen      resim yeni oluşturulan katmana eklenir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Resme motion tween uygulanır(1-15.      kareler arasında mesela)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Resim katmanı aşağı taşınır      böylece buton görülür hale gelir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Buton katmanına sağ tıklayıp      "Mask"a basılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Adım adım geri gidilir.(Şu an      movie clipin içindeyiz. Timeline'in üstünde içine girdiğimiz nesneler      görülür)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Scene1'e gelinip uygulama      oynatılabilir(ctrl+enter)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Görüldüğü üzere animasyon      sürekli hareket etmektedir. Bunu engellemek için küçük bir kod yazmak      gerekir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Tekrar butonun içindeki Over      alanının içindeki movie clipin içine girilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Buradaki mask ve resim katmanının      kilidi kaldırıldığında bunlar üzerinde değişiklik yapılabilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Resim katmanının son karesine      gelinir ve Actions-Frame kısmı açılır. Buraya kod yazılacaktır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Bu karenin kod kısmına </strong></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><strong>stop();</strong></p>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><strong>Yazılır. Ctrl+enter yapıldığında animasyonun bir kez oynayıp durduğu görülür</strong></p>

<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><strong>
</strong>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0 0 0 .375in;"><strong>Resim sabit, buton hareketli:</strong></p>

<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"><strong>
</strong>
<ol style="margin-left:.375in;direction:ltr;unicode-bidi:embed;margin-top:0;margin-bottom:0;font-family:Calibri;font-size:11pt;" type="1">
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>ActionScript 2.0 açılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yeni bir buton oluşturulur</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Türü F8 ile button yapılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Butonun içine girilir over,      down ve hit alanları F6 ile doldurulur</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Over üzerinde iken buton      seçilip movie clip haline getirilir ve ortasındaki yuvarlağa çift tıklanıp      içine girilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yeni bir katman oluşturulur.      Bu resim katmanı olacaktır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Resim bu katmana eklenir,      boyutu ve yeri ayarlanır.</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Bu kez resmin sabit olması ve      butonun hareket etmesi yapılacaktır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Direk resim katmanındaki 20.      karede "Insert Keyframe" yapılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Resim katmanı, buton katmanının      altına sürüklenir. Böylece buton görünür hale getirilir</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Buton katmanında buton için      motion tween oluşturulur(1-20 kareler arası)</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>20inci karede buton      küçültülür</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Buton katmanı seçili iken      katmana sağ tıklanıp "Mask" uygulanır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Yine animasyonun bir kez      hareket edip durmasını istediğimiz için yukarıdaki gibi Actions-Frame      panelinden son kareye stop(); kodu yazılır</strong></span></li>
	<li style="margin-top:0;margin-bottom:0;vertical-align:middle;"><span style="font-family:Calibri;font-size:11pt;"><strong>Ctrl + enter</strong></span></li>
</ol>
<p style="font-family:Calibri;font-size:11pt;margin:0 0 0 .375in;"></p>