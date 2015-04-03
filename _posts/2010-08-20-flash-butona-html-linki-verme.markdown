---
layout: post
title: Flash butona HTML linki verme
date: '2010-08-20 11:22:01'
---

Tümü Flash olan bi uygulamada bu hadise kolayken işin içine HTML girince şöyle bişi yapmak gerekiyor.

- Önce hızlıca bir buton yapalım. Şöyle alelade bir rectangle çiziyorum. Bunun köşelerini yuvarlatmak içinse sol tuş basılıyken yani rectangle'i çizip tam eli kaldıracakken o pozisyonda yukarı ya da aşağı oklarına basmak gerekiyor. İçe ya da dışa doğru yuvarlatmak mümkün.<a href="http://devdala.files.wordpress.com/2010/08/12.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/12.jpg" alt="" width="248" height="90" /></a>- Yazısını da yazalım. Hala Scenedeyiz ona göre daha alt tabakalara inmedik.

<a href="http://devdala.files.wordpress.com/2010/08/21.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/21.jpg" alt="" width="248" height="94" /></a>- Hala Scene deyiz. Henüz rectangle ve yazımız ayrı ayrı şeyler ve buton değil bunlara buton niteliği kazandıralım. ikisini beraber seçip sağ tıklayıp "Convert to symbol"a basıyoruz
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/08/31.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/31.jpg" alt="" width="358" height="360" /></a></p>
<p style="text-align: left;">- Açılan pencereden "Button"ı seçip Ok diyoruz. Artık text ve rectangleimiz buton oldu. Dikkat hala scene deyiz.</p>
<p style="text-align: left;">- Şimdi buton oldu ya şekil. Onun üstüne gelip çift tıklıyoruz ve Scene'den button seviyesine iniyoruz. Flash'ın mantığı bu alt seviyeye inmede yatıyor zaten. Butonun içine girince timeline'da 4 alan görünecek : Up, Over, Down diye. Up butonun normal dururkenki hali, over üstüne mausla gelince hali, down da basıldığındaki hali. Burda oynayabilirsiniz istediğiniz gibi. Ama buralara efekt koymadan önce, hangi alanlarla uğraşılacaksa oralara sağ tıklanıp "Insert Keyframe" yapılmalıdır. Kısayolu da F6. Bunu yapınca Up, over ve down alanlarında siyah içi dolu noktalar çıkacak her birine gelip istediğiniz efekti yaparsınız. Konumuz bu değil neyse. Devam edelim.</p>
<p style="text-align: left;"><a href="http://devdala.files.wordpress.com/2010/08/41.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/41.jpg" alt="" width="499" height="305" /></a></p>
<p style="text-align: left;">- Artık butonumuz hazır. En üst seviye olan Scene'e geri dönüyoruz. Bunun için sahnenin boş bi yerine çift tıklayabilirsiniz. Yani üstteki maddede butonun içine girmiştik ya ondan tekrar çıktık şimdi. Çıktıktan sonra sıra geldi butona link vermeye. Flash'ın actionscript'inde bunun hazır bir fonksiyonu var getURL diye. Onu kullanacağız.</p>
<p style="text-align: left;">Burası önemli küçük bi noktayı kaçırırsanız link olmuyor. Sizin de akıl sağlınız için dikkatli izleyin:D Bu kodu yazmak için Scene'deyken önce sahnenin boş bi yerine tıklıyoruz. Hiç bişeyin seçili olmamasına dikkat edelim. Ettik mi tamam. Buton seçili olmasın yani. Sonra timeline'dan ilk frame'i tıklıyoruz. İçi dolu siyah nokta vardır zaten. Sonra az önce yaptığımız butona tıklıyoruz. Sonra Actions sekmesine gidiyoruz oraya aşağıdaki kodu yazıyoruz:</p>
<p style="text-align: left;"></p>

[php]

on (release) {
 getURL(&quot;http://www.hakanu.net&quot;, &quot;_blank&quot;);
}

[/php]
<p style="text-align: left;">Misal:</p>
<p style="text-align: left;"><a href="http://devdala.files.wordpress.com/2010/08/51.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/51.jpg" alt="" width="433" height="340" /></a>Butonumuz şu şekilde oluyore:</p>
<p style="text-align: left;"><object id="flash1" style="width: 225px; height: 100px;" classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" width="100" height="100" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,40,0"><param name="data" value="http://www.hakanu.net/wp-content/uploads/2010/08/linkliButonBlog.swf" /><param name="quality" value="High" /><param name="src" value="linkliButonBlog.swf" /><embed id="flash1" style="width: 225px; height: 100px;" type="application/x-shockwave-flash" width="100" height="100" src="linkliButonBlog.swf" quality="High" data="http://www.hakanu.net/wp-content/uploads/2010/08/linkliButonBlog.swf"></embed></object>

<p style="text-align: left;">Çalmayın olum bak yazıyı.</p>
<p style="text-align: left;">-Hakan Uysal</p>