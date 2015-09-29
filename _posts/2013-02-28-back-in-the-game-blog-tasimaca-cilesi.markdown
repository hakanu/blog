---
layout: post
title: Back in the game - Blog tasimaca cilesi
date: '2013-02-28 22:14:26'
---

<p style="text-align: center;"> <a href="http://devdala.files.wordpress.com/2013/02/tumblr_m8hj7okpil1ryief6o1_500.gif"><img class="aligncenter" alt="" src="http://devdala.files.wordpress.com/2013/02/tumblr_m8hj7okpil1ryief6o1_500.gif" width="450" height="212" /></a></p>
Upuzun bir aradan sonra blogculuk zanaatina donmus bulunuyorum. Bussuru bussuru yazilcak post listem var. Blog tasima konusunda birkac sacma sapan temel bilgiyi paylasacagim. Bir isi yapan adam sayisi cogaldikca o isle ilgili degerli tamamlayici bilgi miktari da azaliyor. Herkes ayni seyi defalarca yaziyor ve her yazan da insanlarin giris seviyesinde bisileri bilmedigini varsaymiyor.
<h1>Wordpress guncelleme sikintilari</h1>
Wordpress yapisi geregi php karakteristiklerini cok guzel gostermekte. Eski teknoloji olmasindan mutevellit yeni teknolojilerdeki o stabilite mumla araniyor. Isin ilginc yani ise hem joomla hem de wordpress'te hicbir sey degistirmedigim halde site calismamaya basliyordu. Ve yine isin ilginci birkac gun siteyi kendi haline biraktigimda yeniden calisir duruma geliyordu. Yok yok hosting problemlerinden bahsetmiyorum. Onlar ayri hikaye.

Neyse wordpress'e her ne kadar muthis bi sevgi beslesem de bu legacy backendi beni bitiriyor. Onceki blogda her guncellemede sorun cikardi. Eklentiler patlardi, site under constructionda kalirdi, ftp'den girip bi tane php dosyasini silmem gerekirdi falan. Cok korkardim her update'te. Gece falan yapmaya calisirdim usersiz zamanda. Sonra hosting firmasi benim blogu linux'tan windows'a tasidi. Her ne kadar hissedilir bir degisme olmasa da arkada bir seyler bozulmustu. Velhasil iyi oldu bu ferah baslangic.
<h1>Database ile icerigi tasimaca</h1>
Benim blog tasima hikayem biraz el yordamiyla oldu. Dogru durust step by step guide yoktu. Olanlar da 2010'dan falan kalma. Cok cok manuel. Ben benim nasil yaptigimi anlatacagimdir. Sorumluluk almam ona gore.

Onceki hostingin verdigi web panele gidip phpmyadmine girdim. Ordan export kismina geldim. Zipli sekilde indirdim sql dosyasini. Plain texti compress ettigi icin 8 mb'dan 1 mb'a dusmesi isten bile degil. Bu da cok gereksiz bir ayrinti oldu. Daha sonra inen sql dosyasini actim ve icindeki adreslere Ctrl + H caktim. Geditin gozunu seviyim. "devdala.com"lari "hakanu.net" ile degistirdim. Database adini da yeni hostingde cpanel'den yarattigim mysql database'inin adina cevirdim. Sonra modifiye olmus yeni sql dosyasini yeni hostingin cpanel'inden phpmyadmin araciligiyla import ettim. Ve sonra artik wordpress kurulumuna hazirdim. Miydim? Cpanel'in mysql sayfasindan az once yarattigim database'e bir kullanici yarattim. Bu kullaniciya read write accesslerini vermeyi unutmayin sonra uzulmeyin. Sifresini de unutmayin. Az sonra wordpress kurulumuna baslayinca direk sordu. Hemen girdim. Ve bir anda wp-admin sayfasi geldi onume. Tertemiz yeni wordpress'im hazirdi. Son versiyon falan. Pluginlerim, temalarim yoktu ama olsun. Onlari kurmasi zevkli bir procrastination.

Sorun su ki simdi ayni icerige sahip iki sitem vardi ki domainleri farkli oldugundan hic de hos bir durum degildi. Nasil redirect ederim diye sorusturdum. En sonunda soyle bir yontem buldum: 301 redirection. http 301 headeri iki cevap donduruyor. Birisi "permanently moved" ve digeri yeni site adresi. Boyle oldugu zaman gugil icin de iyi oluyormus. Hemen yeni hostingin cpaneline gittim. Yeni bir domain park ekle dedim. Ordan devdala.com ve hakanu.com'u ekledim. Sonrasinda da bu yonlendirmeleri hakanu.net'e 301 ile yonlendir dedim. Chrome webmaster tools'tan network tabindan bakinca gayet de 301 response'u gorunuyor. Yaptim sanirim.

Domainlerin listesi:

<a href="http://hakanu.net" target="_blank">hakanu.net</a>

<a href="http://hakanu.com" target="_blank">hakanu.com</a>

<a href="http://devdala.com" target="_blank">devdala.com</a>

<a href="http://hakanu.co" target="_blank">hakanu.co</a>

Simdilik boyle. Yakinda buralar sacma sapan postlarla dolacak.