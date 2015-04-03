---
layout: post
title: Opencv'yi CUDA desteği ile derlemek ve kullanmak - Opencv 2.3
date: '2011-08-09 21:58:06'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/08/bscap0381.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/bscap0381.jpg" alt="" width="605" height="340" /></a></p>
Öncelikle cuda desteği olmadan çıkarılmış release sürümü kurmam lazım. Onun anlatımı şurda idi (Onu halledip aşağıdan devam etmeli):

<address><a title="Opencv kurulumu – Opencv 2.3" href="http://www.hakanu.net/?p=1817" rel="bookmark inlinks permalink">Opencv kurulumu – Opencv 2.3</a></address>Baştan söyliyim cmake'i çok seveceksiniz. Opencv 2.2 sürümünden itibaren ekran kartı desteği vermeye başlamış olsa da varsayılan olarak bu özellik kapalı olarak geliyor. Kütüphaneyi tekrar derlemek gerekiyor.

- Kurduğumuz yere gidiyoruz ve OpenCV2.3\opencv klasörünün altında "CMakeLists.txt" dosyasını buluyoruz. Bunu tutup cmake e atıyoruz.

- Configure'e basıyoruz. Compileri soracak. Ona ben VS 2010'u seçtim (10).

- Daha sonra hangi parametrelerle kod üreteceğini soruyor Cmake. Bu noktada değiştirilmesi gereken parametre "WITH_CUDA". Bunun işaretli olduğundan emin olun. Ben "BUILD_EXAMPLES"ı falan da işaretledim. Pythonları seçmedim. Zaten sdkları yüklü olmadığı için hata veriyor işaretlesem de. Ondan sonra tekrar Configure'e basın. Tabi bunu yapabilmesi için bilgisayarda Cuda Toolkit kurulu olmalı. Kurulu değilse şurdan ulaşılabilir:

<a href="http://developer.nvidia.com/cuda-toolkit-40">http://developer.nvidia.com/cuda-toolkit-40</a>

KüçükNot: Qt'nin yüklü olmasına gerek yok bilgisayarınızda eğer işiniz yoksa. Ekran görüntüsüne çok bağlı kalınmamasına.

- Generate'e basılır.
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/08/opencv-71.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-71.png" alt="" width="627" height="509" /></a></p>
<p style="text-align: left;">- Cenereyşın bitince opencv'nin kurulu olduğu klasörde VS 2010 solution dosyalarının çıktığı görülür.</p>
<p style="text-align: left;">- Opencv.sln açılır. "Build solution" denir. Ve her şey zamana bırakılır.  Bilgisayarın hızına göre değişse de bi yarım saat sürüyor bu süreç. Ekran kartı desteği (Gpu support) ile derleniyor kütüphaneler. Lib uzantılı dll uzantılı çıktıları üretiliyor. Dll ler --&gt; OpenCV2.3\opencv\bin\Debug burda iken Libler OpenCV2.3\opencv\lib\Debug buraya çıkıyor.</p>
<p style="text-align: left;">- Deneme için OpenCV2.3\opencv\samples\gpu yolundaki gpu.cpp'yi kullanabiliriz. Yeni proje açıp bu kodu yapıştırdıktan sonra projeye opencv bağımlılıklarını ekleyerek ki bunlar <a title="Opencv kurulumu – Opencv 2.3" href="http://www.hakanu.net/?p=1817" rel="bookmark inlinks permalink">Opencv kurulumu</a>'nda anlatılmıştı derlemeye hazır hale getirebiliriz. Build ettikten sonra solution'ı çıktı klasörüne gidip exe'yi çalıştırabiliriz.</p>
<p style="text-align: left;">- exe sample olduğu için çalıştırmanın yolu yordamı var. Bir tane imaj dosyası vermemiz gerekiyor çalışması için. Videodan falan da çalışabilir parametrelere göre. Ctrl+r yapıp cmd yazıp komut satırını açıyoruz. cd ile exe'nin olduğu yola geliyoruz. Exe'yi çalıştırma kodunu yazıyoruz.</p>

<pre style="text-align: left;">OpencvOrnek2Gpu.exe --src road.png</pre>
<p style="text-align: left;">Gerisi resimde zaten:</p>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/08/opencv-gpu.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-gpu.png" alt="" width="537" height="628" /></a></p>
<p style="text-align: left;">------</p>
<p style="text-align: left;">Aynı kodu gpu support ile derlenmemiş liblerden oluşturup yine aynı şekilde gpusuz dll lerin yanına koyarsak şöyle bir uyarıyla karşılaşmamız kuvvetle muhtemel:</p>

<blockquote>
<p lang="en-US">The library is compiled without GPU support</p>
</blockquote>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/08/opencv-gpu2.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-gpu2.png" alt="" width="532" height="311" /></a></p>