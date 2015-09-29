---
layout: post
title: Ubuntu'da çok tuşlu farelerin kurulumu-tuşların aktifleştirilmesi
date: '2009-10-01 21:40:26'
---

Çok tuşlu fare ve klavyeleri seven bir yapıya sahip olduğum için Windows altında kullandığım multimedya özelliklerini Linux altında kullanmak istiyorum ben. Bilmiyorum haksız mıyım. Eğer sizin de 6-7 tuşlu fareniz var ve tuşları aktif değilse aşağıdaki yöntemi kullanabilirsiniz. (Anlatımın orjinali İtalyanca bir sitede. Girmek için <a href="http://natonelbronx.wordpress.com/2007/07/10/mouse-a4tech-x7-con-linux-facciamo-funzionare-tutti-i-tasti/">buraya</a> tıklayabilirsiniz. Türkçe'ye çeviren arkadaş için <a href="http://forum.ubuntu-tr.org/index.php?topic=159.0">buraya</a> tıklayabilirsiniz. Ben onun anlattığı yöntemi kendi uyguladığım şekliyle anlatacağım)

Öncelikle evdev adlı pakedi güncelliyoruz. Bunun için Uygulamalar -&gt; Donatılar -&gt; Uçbirim yolunu izleyerek terminal açıyoruz ve aşağıdaki kodları sırayla yapıştırıp entera basıyoruz:
<pre style="margin-top: 0; display: inline;">sudo apt-get update</pre>
<div><span style="font-family: Consolas, Monaco, monospace;"><span class="Apple-style-span" style="font-size: 12px; line-height: 18px; white-space: pre;">
</span></span>
<div>
<pre style="margin-top: 0; display: inline;">sudo apt-get install xserver-xorg-input-evdev</pre>
Ardından yine terminale aşağıdaki kodu yapıştırıp entera basıyoruz:
<pre>cat /proc/bus/input/devices</pre>
Bu komut ile sisteme takılı donanımların listesi terminalde görünecektir. Buradan farenizle ilgili kısmı bulun. Benimki şöyle:

<img class="size-full wp-image-405 alignnone" title="1" src="http://devdala.files.wordpress.com/2009/10/1.png" alt="1" width="495" height="162" />

Handlers yazan satırdaki event kısmına dikkat etmek gerekir. Ben kendiminki olan event4 olarak devam ettim işleme. Siz de kendinizkine göre devam edin.

Şimdi xorg.conf adlı dosyada birkaç değişiklik yapacağız.

Önce bir yedeğini alıyoruz:
<pre style="margin-top: 0; display: inline;">sudo cp /etc/X11/xorg.conf /etc/X11/xorg.conf.yedek</pre>
Herhangi bir sorunda kurtarma modunda aşağıdaki kod yazılarak geri dönüş yapılabilir:
<div>
<pre style="margin-top: 0; display: inline;">sudo cp /etc/X11/xorg.conf.yedek /etc/X11/xorg.conf</pre>
</div>
Sonra düzenlemek için xorg.conf dosyasını açıyoruz. Benimkinin fare ile ilgili kısmı şöyleydi:

<img class="size-full wp-image-407 alignnone" title="ilkHal" src="http://devdala.files.wordpress.com/2009/10/ilkhal.png" alt="ilkHal" width="372" height="140" />

Burada birkaç değişiklik yapmamız gerekiyor. Öncelikle ilk satıra yani Identifier yazan satıra dokunmuyoruz. Altındaki satırdaki "mouse"u "evdev" yapıyoruz. Onun altındaki satırın başına # koyuyoruz. Böylece o satır etkinsizleştirilir. Dilerseniz o satırı silebilirsiniz de. Bir alt satırdaki "/dev/input/mice" kısmını "dev/input/event4" yapıyoruz. Tabi event4'ü herkes yukarıda event numarası kaç ise ona göre değiştirmelidir. Benimki event4 olduğu için öyle yaptım. Bir alttaki satırı ellemiyoruz. Onun altındaki satıra yukarıda terminalde faremiz ilgili kısımdaki Name'in karşısındaki değeri yazdım. Yani "A4Tech PS/2+USB Mouse" yazdım. İtalyanca sitedeki şahıs,  "A4Tech X7" yazmış. Sonuç olarak
<pre style="margin-top: 0; display: inline;">Option          "Name"	"A4Tech X7"</pre>
diye bir satır eklenmelidir buraya.

Daha sonra bir alttaki satırın başına da # konur. Böylece o satırda etkinsizleştirilir. Benim xorg.conf'umun fare ile ilgili kısmının son hali şöyle:

<img class="alignnone size-full wp-image-409" title="sonHal" src="http://devdala.files.wordpress.com/2009/10/sonhal.png" alt="sonHal" width="447" height="139" />

Kaydedip kapatıyoruz. Sistemi yeniden başlatıyoruz.

Şöyle bir kod daha var ama ben bunu çalıştıramadım hata verdi. Olmasa da olur sanırım. Eski sürümler için olabilir.(benim sürüm 9.04):
<pre style="margin-top: 0; display: inline;">xmodmap -e "pointer=1 2 3 4 5 8 9 6 7"</pre>
Terminale şu kodu yazıyoruz şimdi de:
<pre style="margin-top: 0; display: inline;">xev | grep button</pre>
Şöyle bir pencere açılacak:

<img class="alignnone size-full wp-image-412" title="grepButton" src="http://devdala.files.wordpress.com/2009/10/grepbutton.png" alt="grepButton" width="143" height="163" />

Bu pencerede farenin tuşlarını basarak terminalde kaç numaralı tuşa denk geldiğini görebilirsiniz.

xmodmap'in varsayılan sırası şu şekilde: 1 2 3 4 5 8 9 6 7

Buradaki 8 ve 9'a dokunmuyoruz. Onlar farenin kendi ayarları ile ilgiliymiş.

Sıra Xmodmap'i kendimize göre düzenlemeye geldi. Bunun için terminale aşağıdaki kodu yazıyoruz:
<div>
<pre style="margin-top: 0; display: inline;">gedit .Xmodmap</pre>
Boş bir sayfa çıkacak. Benim karşıma çıkan doluydu gerçi(Aşağıdaki satır yazıyordu). Ama boş çıkarsa şunu yazın:
<pre style="margin-top: 0; display: inline;">pointer=1 2 3 4 5 8 9 6 7</pre>
<p style="margin-bottom: 0;">Kaydedip kapatın ve sistemi yeniden başlatın. Artık tuşlar aktif hale gelecektir. xmodmap sırasını değiştirerek fare tuşlarını ayarlayabilirsiniz.</p>
<p style="margin-bottom: 0;">Not:Eğer hala Firefox veya Opera'da farenin orta tuşuna basıp sürükleme yapamıyorsanız bu fare ayarlarından değil tarayıcı ayarlarındandır. "Otomatik kaydırmayı" aktifleştirmek gerekir.</p>
<p style="margin-bottom: 0;"><em>Firefox'ta "otomatik kaydırma"yı aktifleştirmek için:</em></p>
<p style="margin-bottom: 0;">Düzen -&gt; Seçenekler -&gt; Gelişmiş -&gt; Otomatik kaydırmayı kullan</p>
<p style="margin-bottom: 0;"><em>Opera'da bu özelliği aktifleştirmek için:</em></p>
<p style="margin-bottom: 0;">Shift + farenin orta tuşu(scroll)'na basılır, çıkan pencerede "Orta tuş görevini belirleyin" kısmında "Gezdiremeye başla" işaretlenir</p>

</div>
</div>
</div>