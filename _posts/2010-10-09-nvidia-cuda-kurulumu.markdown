---
layout: post
title: NVIDIA CUDA Kurulumu
date: '2010-10-09 08:22:36'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/nvidia-logo.jpg"><img class="aligncenter" title="nvidia logo" src="http://devdala.files.wordpress.com/2010/10/nvidia-logo.jpg" alt="" width="168" height="168" /></a></p>
Yine Türkçe kaynağı çok çok az olan bir konu bu. Kurulum kolay ama yine de sırayla yapmakta fayda var.

1) Öncelikle ekran kartımız CUDA'ya müsait mi diye bakıyoruz. Onun için şuraya gidiyoruz:
<div id="_mcePaste">- NVIDIA GeForce® 8, 9, 200 ve 400 serileri</div>
<div id="_mcePaste">- NVIDIA Tesla™</div>
<div id="_mcePaste">- NVIDIA Quadro® ürünlerinin çoğu</div>
<div>Ayrıntılı bakmak isteyenler için:</div>
<a href="http://www.nvidia.com/object/cuda_gpus.html" target="_blank">CUDA'ya sahip ekran kartları listesi</a>

2) Bizim CUDA kullanabilmemiz için gerekenler:

- CUDA enabled bi GPU

- GPU'nun driveri

- CUDA yazılımı

- Visual Studio 2005, 2008 veya Visual C++ Express

3) 1. maddedeki listeye bakıp ekran kartımızın CUDA desteğini içerdiğini anladık mı tamam devam edelim. Şimdi onun driverini kurmaya geldi sıra. Her zaman güncel driverları kullanmakta fayda var. Driver sürümüyle CUDA SDK ve toolki sürümü aynı olmalıdır aksi halde sorun çıkmaktadır. Driverları şuradan bulabiliriz:

<a href="http://www.nvidia.com/Download/index.aspx?lang=en-us" target="_blank">Download Nvidia Drivers</a>

Şu adreste CUDA için gerekli olan bütün her şeyin listesi var yalnız buradaki developer driverlarını kurunca benim Windows 7 çöktü. Sizde nolur bilmiyorum.

<a href="http://developer.nvidia.com/object/cuda_3_2_toolkit_rc.html" target="_blank">Nvidia CUDA için gereken her şey</a> (Yazıyı yazarken CUDA 3.2 RC versiyonundaydı)

Eski sürümlerine ulaşmak için ise şuraya gidiyoruz:

<a href="http://developer.nvidia.com/object/cuda_archive.html" target="_blank">Nvidia CUDA Toolkit eski sürümleri</a>

Şimdi eski sürümleri niye verdim şunun için sizin kurduğunuz driver üstündeki CUDA versiyonu eski olabilir ama siz gidip de uyuşmayan daha yeni bir CUDA kurarsanız patlama olasılığı çok yüksek. Şahsen yaşadım biliyorum.

Öncelikle yüklediğimiz driverimizi bir doğrulayalım acaba içinde CUDA var mı varsa versiyonu kaç:

- Masaüstünde boş bi yerde sağ tıklayıp "NVIDIA Control Panel"e geliyoruz. Ordan açılan pencerenin sol alt köşesindeki "System Information"a basıyoruz.  Orda CUDA çekirdeği sayınızı da görebilirsiniz. Ne kadar çok o kadar iyi:) bi gtx 480imiz yok ki 480 CUDA cores yazsın. Neyse sapmayalım olaydan

- Üst sekmelerden "Components"e basıyoruz. Orda CUDA driver versiyonu yazar. Misal bendeki:

<a href="http://devdala.files.wordpress.com/2010/10/cudasysinfo.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/cudasysinfo.jpg" alt="" width="569" height="228" /></a>

Burda benim CUDA versiyonum 3.1 mesela. Şu an 3.2 RC var. Ben de hemencecik en günceli olsun diye CUDA Toolkit 3.2'yi kurmuştum. Deneme uygulaması çalıştırdım. "Version mismatch" dedi.  Toolkitleri falan kaldırıp 3.1 indirip tekrar kurmak zorunda kaldım. Sonra oldu neyse ki. Devam edelim.

4) Driver versiyonumuza uygun CUDA Toolkitini indirmemiz gerekiyor. Tekrarlıyorum yukarıda Toolkit adresleri var oralardan size uygun olanı çekin. Benim versiyonum 3.1 olduğu içn ondan devam edeceğim anlatmaya. CUDA 3.1 versiyonu şuradan indirilebiliyor.

<a href="http://developer.nvidia.com/object/cuda_3_1_downloads.html" target="_blank">Nvidia CUDA 3.1 gereken her şey</a>

5) Yukarıdaki linke girip scrollu azcık aşağı çekip şunu indiriyoruz: <span style="font-family: Verdana, Geneva, Arial, Helvetica, 'Sans Serif'; line-height: normal; font-size: 11px; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;">"CUDA Toolkit" </span>ndi tabi 32 bit/64 bit olayına da dikkat edin.

<span style="font-family: Verdana, Geneva, Arial, Helvetica, 'Sans Serif';"><span style="line-height: normal; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;"><span style="font-family: Georgia, 'Times New Roman', 'Bitstream Charter', Times, serif; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; line-height: 19px;">6) Bunun arkasına CUDA SDK'yı indirmemiz gerekiyor. Yeni versiyonlarda adı biraz aldatmacalı olmuş ama olsun. SDK için de şunu indiriyoruz -yine yukardaki linkten, içinde bol miktarda sample var-:</span></span></span>

<span style="font-family: Verdana, Geneva, Arial, Helvetica, 'Sans Serif';"><span style="line-height: normal; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;"><span style="font-family: Georgia, 'Times New Roman', 'Bitstream Charter', Times, serif; -webkit-border-horizontal-spacing: 0px; -webkit-border-vertical-spacing: 0px; line-height: 19px;"><span style="font-family: Verdana, Geneva, Arial, Helvetica, 'Sans Serif'; line-height: normal; font-size: 11px; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;">GPU Computing SDK code samples</span></span></span></span>

<span style="font-family: Verdana, Geneva, Arial, Helvetica, 'Sans Serif'; line-height: normal; font-size: 11px; -webkit-border-horizontal-spacing: 2px; -webkit-border-vertical-spacing: 2px;"> </span>

7) Önce CUDA Toolkiti kuruyoruz. Arkasına GPU Computing SDK code samples'ı kuruyoruz.

8) Kurulumdan sonra masaüstünde "NVIDIA GPU Computing SDK Browser" isimli bi kısayol çıkacak onu açıyoruz. Karşımıza 100'den fazla örnek çıkacak. Onlar incelenebilir.

9) Deneme yapmak için -şiddetle tavsiye edilen- "Bandwidth Test" gelip "Run" diyelim.  Çalıştıktan sonra "PASSED" dediyse sorun yok. Diğer uygulamaları da çalıştırabilirsiniz. Acayip şeyler de var orda. Hadi bakalım.

Orjinal belgeden kurarım diyenlere gelsin:

<a href="http://developer.download.nvidia.com/compute/cuda/3_1/docs/GettingStartedWindows.pdf" target="_blank">Nvidia CUDA getting started guide</a>

Visual Studio kullanmak isteyenler için ise

<span style="color: #333333; font-family: 微软雅黑, Helvetica, Times, Arial, serif; line-height: 18px;"> </span>

<a class="icon" style="color: #2f63b3; text-decoration: none; outline-style: none; background-image: url(http://www.hakanu.net/wp-content/themes/philna2/images/icon.gif); background-attachment: initial; background-origin: initial; background-clip: initial; background-color: initial; background-position: 100px 100px; background-repeat: no-repeat no-repeat;" title="Visual Studio’yu CUDA için hazırlamak ve ilk CUDA programını derlemek" rel="bookmark inlinks permalink" href="http://www.hakanu.net/?p=1540">Visual Studio’yu CUDA için hazırlamak ve ilk CUDA programını derlemek</a>