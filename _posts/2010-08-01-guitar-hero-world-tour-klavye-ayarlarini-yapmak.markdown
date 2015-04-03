---
layout: post
title: Guitar Hero World Tour klavye ayarlarını yapmak
date: '2010-08-01 18:06:34'
---

Guitar Hero'yu benim gibi evde klavyeyle oynmaya uğraşan garibanlardansınız iyi dinleyin.  iii'te klavyeyi ayarlarken oyun çöküyordu gidip xml'i elimizle değiştirmek icap ediyordu. World tour'da hiç ayar ekranı bile yok. Direk xml ile oynamak şart oluyor. Oynarken dikkat edin bebekler karıştırınca karışıyor valla. Xml'i direk üreten bi site varmış keyconfig.com diye kapanmış o da. Yana döne ararken en sonunda başka bi site buldum fıstık gibi xml üretiyor. Anlatıyorum dinle:

1) <a href="http://steves3d.co.uk/" target="_blank">http://steves3d.co.uk/</a> buraya giriyoruz

2) "Run GH Keys"e basıyoruz ve tadaa bir flex application karşımıza cıkıyor

3) Orda istediğimiz kontrolleri ayarlayınca xml altta üretiliyor. O xml'i kopyalıyoruz

4) Klavye ayarlarının tutulduğu config xml'i şurda konuşlanmış durumda(Vista ve Windows 7'de yer değişebilir buna benzer bi yerde yine bulursunuz siz):
<pre>C:\Documents and Settings\hakan\Local Settings\Application Data\Aspyr\Guitar Hero World Tour</pre>
5) Burdaki "AspyrConfig.xml" dosyasını açıp az önce application'dan kopyaladığımız kodları yapıştırıyoruz. Her ihtimale karşı bu xml'in yedeğini alın da bi sakatlık olmasın.

6) Kaydedip çıkıyoruz. İyi oyunlar gençler.