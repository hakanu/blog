---
layout: post
title: Visual Studio'yu CUDA için hazırlamak ve ilk CUDA programını derlemek
date: '2010-10-28 22:58:02'
---

<h3><a href="http://devdala.files.wordpress.com/2010/10/cuda.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/cuda.jpg" alt="" width="252" height="252" /></a></h3>
<span style="font-weight: normal;">Şurda kurulumdan bahsetmiştim </span>

<a title="NVIDIA CUDA Kurulumu" rel="bookmark inlinks permalink" href="http://www.hakanu.net/?p=1533">NVIDIA CUDA Kurulumu</a>

Şimdi sıra geldi CUDA geliştirilecek olan ortamı hazırlamaya. Nvidia iyi etmiş güzel etmiş de şöyle bi yüklemede olabilen bi Visual Studio eklentisi yapmamış. Ya da ben bulamadım bilmiyorum. Official olarak yok yani. Unofficial Cuda Wizardları var da gerek yok. Şimdi anlatcam ben. Burda dikkatli edilmesi gereken husus hangi CUDA Toolkitini kuracağınız. Şu anda 28.10.2010 itibariyle 3.2 RC yayında. Ben hem 3.2'yi hem 3.1'i anlatacağım.
<h2 style="text-align: center;"><strong>Nvidia CUDA Toolkit 3.2 RC için konfigürasyon:</strong></h2>
Önce kolaydan başliyim. Bunun içine Nvidia hem visual studio konfigurasyon dosyalarını gömmüş hem de build rule dosyalarını. Böylece bize daha az iş kalıyor. Yapılması gerekenler:

1) <strong><span style="color: #993300;">CUDA dosyaları için renklendirme: </span></strong>Visual Studio 2008(veya 2008 SP1)'i açıp  Tools -&gt;Options -&gt; Text Editor -&gt; File extension'a geliyoruz. Extension kısmına "cu" yazıyoruz tabi ki tırnaklar olmadan. "Microsoft Visual C++" seçip add diyoruz. Artık cu dosyaları renklenecek.
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-1.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-1.jpg" alt="" width="605" height="351" /></a></p>
<p style="text-align: center;"></p>
2) <span style="color: #993300;"><strong>CUDA dosyaları için intellisense'i etkinleştirmek: </strong></span>Bu büyük ihtimalle etkin olarak gelecek. Etkin değilse de elimizle konfigure edebildiğimiz gibi Nvidia sağolsun bu toolkitte şöyle bir reg dosyası hazırlamış. Onunla da ayarlanabilir. Bu reg dosyasının konumu şurada -ben buraya yükledim SDKyı-:
<blockquote>
<pre>C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v3.2\extras\visual_studio_integration</pre>
</blockquote>
Bu klasörün altında "gpucomputing_intellisense.reg" var onu çalıştırınca kayıt defterine cu ve cuh uzantılı dosyalar için intellisense'i etkinleştirme olayını ekliyor.

3) <span style="color: #993300;"><strong>CUDA dosyalarını derleme/build etme: </strong><span style="color: #000000;">Yeni toolkit ile bu da kolaylaştırılmış. Önceki versiyonda elimizle cuda.rules'ı custom build rule olarak tanımlayıp konumunu gösterip seçip derletiyorduk. Şimdi olay basitleşmiş. Visual Studio'nun klasörlerinin ilgili yerlerine Nvidia kendi rules dosyalarını kopyalamış oluyor. Bize kalan tek şey Projeye sağ tıklayıp Custom Build Rules'a basıp en altın bi üstündeki "CUDA Runtime Api Build Rule (v3.2)"yi işaretleyip OK diyoruz. Artık nvcc kullanarak derleme yapılabilir. Tabi daha işimiz bitmedi.</span></span>
<p style="text-align: center;"><span style="color: #993300;"><span style="color: #000000;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-2.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-2.jpg" alt="" width="267" height="451" /></a>
</span></span></p>
<p style="text-align: center;"><span style="color: #993300;"><span style="color: #000000;"> </span></span></p>
<p style="text-align: center;"><span style="color: #993300;"><span style="color: #000000;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-3.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-3.jpg" alt="" width="539" height="346" /></a>
</span></span></p>
<span style="color: #993300;"><span style="color: #000000;">Bu noktaya kadar her şeyi yapıp başarılı olunduysa "Visual Studio ile ilk projenin derlenmesi" kısmına atlayın yazının.</span></span>
<h2 style="text-align: center;"><strong>Nvidia CUDA Toolkit 3.1 için konfigürasyon:</strong></h2>
1) Öncelikle elimizde Visual Studio 2008 olmalı. C'de yüklü olursa daha iyi olur. Başınız ağrımaz. D'de yüklü olunca ortam değişkenlerini falan ayarlamak gerekiyor. Şimdi de ayarliciz gerçi de o kadar değil. CL.exe'yi kullanacak çünkü bizim nvcc.exe CUDA derleyicisi. VS 2008 kurulduktan sonra(SP1 de kurulabilir. Şayet Nvidia Parallel Nsight kullancam ben diyen arkadaşların yüklemesi şart zaten. SP1 yüklü değil diyor daha setupta)

2) <span style="color: #993300;"><strong>CUDA dosyaları için renklendirme:</strong></span> Şimdi Visual Studio'nun "cu" uzantılı dosyaları tanıyıp renklendirmesini(syntax highlighting dediğimiz olay) sağlamak lazım. Cuda sözdizimi C++ gibi azcık değişik zaten.  Bu uzantıyı eklemek için Visual Studio'yu açıp Tools -&gt;Options -&gt; Text Editor -&gt; File extension'a geliyoruz. Extension kısmına "cu" yazıyoruz tabi ki tırnaklar olmadan. "Microsoft Visual C++" seçip add diyoruz. Artık cu dosyaları renklenecek.
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-1.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-1.jpg" alt="" width="605" height="351" /></a></p>
<p style="text-align: center;"></p>
3)<span style="color: #993300;"><strong> CUDA dosyaları için intellisense'i etkinleştirmek:</strong></span> Başlat -&gt; çalıştır açıp regedit.exe yazıyoruz ve kayıt defterini açıyoruz. Ordan şu kayıda gidiyoruz:
<blockquote>
<pre>HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\9.0\Languages\Language Services\C/C++</pre>
</blockquote>
Ordaki cpp falan olan kaydı açıyoruz ve şunları ekliyoruz:
<blockquote>
<pre>.cu;.cuh</pre>
</blockquote>
Artık Visual Studio cu uzantılı dosyalarda da intellisense'i açıp code complete yapacak.

4) <strong><span style="color: #993300;">CUDA dosyalarını derleme/build etme:</span></strong> Bunun için Nvidia bir rules dosyası hazırlamış onu kullaniciz. Yeni bir C++ Win32 console application oluşturuyoruz. Empty project yapıyoruz. src'nin içine yeni bir item ekliyoruz. cpp dosyası ekleyip adını .cu uzantılı yazabilirsiniz. Ya da cu dosyasını sürükleyip src'nin içine atabilirsiniz. Hiç farketmez. hello.cu misal. Neyse bunu yaptıktan sonra Solution Explorer'dan olabilir mesela projemize sağ tıklayıp "Custom Build Rules"a basıyoruz. Çıkan pencerede "Find existing"e basıyoruz. Aradığımız dosya "rules" uzantılı Cuda.rules dosyası. Şu konumda olmalı yani en azından bende orda:
<blockquote>
<pre>C:\ProgramData\NVIDIA Corporation\NVIDIA GPU Computing SDK\C\common</pre>
</blockquote>
Sizde yoksa burda arattırın bilgisayarda. SDK'yı kurduysanız elbet gelmiştir bir yere. Bu dosyayı ekleyip başına da tik attık mı tamamdır. OK diyip çıkıyoruz. Yalnız bu build rule ayarlama olayını her yeni proje açılışında yapmak gerekiyor. Her seferinde dosyayı bulmak değil de CUDA Build Rule'a tik atmak gerekiyor.
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-2.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-2.jpg" alt="" width="267" height="451" /></a></p>
<p style="text-align: center;"></p>
5) Artık her şey hazır. Tabi görünen kısım bu. Görünmeyen kısım bu kadar kolay değil. En azından bana zor oldu. Adam gibi Visual Studio kullanmayı bilmeyince. Artık sıra ilk kodu derlemede
<h2 style="text-align: center;"><strong>Visual Studio ile ilk projenin derlenmesi:</strong></h2>
Projeyi açtık, custom build rule'u seçtik. src'nin içine yeni bi cpp dosyası yaratmaya girilir. Adını cu uzantılı bişiler konur. Uzantısı cu olmalı yoksa sözdizimsel hatalar geliyor. CUDA syntaxi değişik sonuçta az biraz. Sonra kod derlenir. Şimdilik örnek kodlar üzerinden gidelim. SDK'da Nvidia bizi düşünmüş ve büssürü örnek proje koymuş. SDK'yı kurunca onlar da geliyor haliyle. Bulundukları lokasyon:
<blockquote>
<pre>C:\ProgramData\NVIDIA Corporation\NVIDIA GPU Computing SDK 3.2\C\src</pre>
</blockquote>
Böyle bişi olmalı. SDK'nın alt klasöründe yani. Tavsiye edilen buradaki "bandwidthTest"i derleyip çalıştırmaktır. Solution açıldığı vakit zaten kendiliğinden custom build rules'u seçilmiş olur. Biz de renklendirme ayarını yaptığımız için intellisense ve renklendirme de olacaktır. Start Debuging diyince büyük ihtimal çalışması lazım. Çalışmazsa muhtemelen gerekli kütüphaneleri bulamamıştır. Onların nasıl Visual Studio'ya gösterileceği konusuna ileriki bir yazıda değineceğim.

BandwidthTest'in çıktısı şöyle bişi olmalı:
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-4.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/nvidia-cuda-4.jpg" alt="" width="542" height="318" /></a></p>
<p style="text-align: center;"></p>
<em>- Hakan Uysal</em>
<div><span style="color: #0000ee; -webkit-text-decorations-in-effect: underline;">
</span></div>