---
layout: post
title: Windows 7&#039;yi usb bellek ile kolayca kurmak
date: '2009-10-08 22:26:44'
---

Her ne kadar Windows 7'yi USB sürücüden kurmanın birçok yöntemi olsa da bu en kolay olanı. Hiç bir DOS komutuna ihtiyaç yok. 2 tıkla kendi Windows 7 kurulum flash belleğinizi hazırlayabilirsiniz. Windows 7'yi USB'den kurmak çok daha hızlı.

Gereksinimler:

1. USB bellek(4 GB minimum)

2. Windows 7 ISO imaj dosyası

3. UNetbootin

Öncelikle UNetbootin'i indiriyoruz. Windows için <a href="http://sourceforge.net/projects/unetbootin/files/UNetbootin/372/unetbootin-windows-372.exe/download" target="_blank">buradan</a> indirebilirsiniz. Kurmaya gerek yok sadece UNetbootin.exe dosyasına çift tıklayıp çalıştırın. Şimdi <strong>Diskimage </strong>kısmını seçip daha önceden indiriğiniz Windows 7 ISO dosyasını seçin.  <strong>Type </strong>kısmını ise USB Drive seçin ve <strong>Drive </strong>kısmındaki harfe de USB belleğinizin harfini seçin. Bunları yapınca oluşması gereken ekran şu şekilde olmalıdır:

<img class="aligncenter size-full wp-image-523" title="3921508540_662ea77ba1_o" src="http://devdala.files.wordpress.com/2009/10/3921508540_662ea77ba1_o.png" alt="3921508540_662ea77ba1_o" width="455" height="334" />

OK butonuna basın. Dosyaların USB belleğe kopyalanıp açılması yaklaşık 10-15 dakika sürer. Bittikten sonra artık USB belleğiniz bootable olmuştur.(Yani bilgisayar USB bellekten başlatılabilir hale gelmiştir.)

Daha sonra bilgisayarı yeniden başlatın. DEL tuşuna basıp BIOS ayarlarına girip başlatma araçlarının önceliğinden USB sürücüleri 1. yapın. Tekrar baştan başlattığınızda USB sürücü bilgisayara takılıysa Windows 7 yüklenme ekranı görünecektir.

UNetbootin, Linux için de çalışmaktadır. Linux versiyonunu <a href="http://sourceforge.net/projects/unetbootin/files/UNetbootin/372/unetbootin-linux-372/download" target="_blank">buradan </a>indirebilirsiniz.