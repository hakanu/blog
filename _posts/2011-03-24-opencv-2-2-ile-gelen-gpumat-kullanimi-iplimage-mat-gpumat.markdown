---
layout: post
title: OpenCV 2.2 ile gelen GpuMat kullanımı - IplImage, Mat, GpuMat
date: '2011-03-24 00:04:45'
---

Bir aydan sonra son umutsuz denememin ardından OpenCV 2.2'yi CUDA enabled halde derleyebildim. Cahil olmamak lazım. Neyse OpenCV 2.2 ile birlikte kısmi CUDA desteği geldi. Fonksiyonların bi kısmını port etmişler. Sakın ola Canny'yi kullanmayın. Çünkü buglı bi fonksiyon. OpenCV'den gelmiyor tabi bug. CUDA Toolkit 4.0 RC'ye baktığımda o fonksiyonun toolkitten çıktığını gördüm. Bir haftamı yemişti çalıştırmaya uğraşmak. Buglı olduğu için çıkardılar sanırım.

OpenCV 2.2 ile güzel bir veri yapısı geliyor <strong>GpuMat </strong>diye. Gpu üzerinden malloc yapıyor. Resimler için yer alıyor. Kullanımını fevkalade minimalist yapmışlar. Super bir de interoperability koymuşlar. Daha önceki klasik OpenCV veri yapıları olan Mat ile IplImage ile güzel bir uyumu var.

Küçük bir örnek yapalım:

[php]IplImage *hostImg = cvLoadImage(&quot;C:\\Temp\\monas.jpg&quot;);

Mat m(hostImg);

GpuMat g(m);

imshow(&quot;Deneme&quot;, g);

waitKey(0);[/php]

Doğrudan <strong>IplImage*</strong>'dan şöyle de <strong>GpuMat </strong>oluşturulabiliyor:

[php]GpuMat g(hostImg);[/php]

<strong>imshow </strong>ile bu 3 veri yapısı da kullanılabiliyor:

[php]imshow(&quot;Deneme&quot;, m);[/php]

[php]imshow(&quot;Deneme&quot;, hostImg);[/php]

OpenCV referans sitesinde baktığımda en basit GPU örneğinin çalıştıramadım. Orda doğrudan bir Mat'tan GpuMat'a atama var. Direk derlemede hata veriyor. Bana da biraz garip gelmişti. Bi kere memory adres evrenleri farklı. Kısmet hep.

Ve tabi ki unutmadan kullanılan header ve namespaceler (fazla header var):
<div id="_mcePaste"><span style="font-family: Consolas, Monaco, 'Courier New', Courier, monospace; line-height: 18px; white-space: pre;">[php]#include &lt;opencv2/imgproc/imgproc.hpp&gt;
#include &lt;opencv2/gpu/gpu.hpp&gt;
#include &lt;opencv2/highgui/highgui.hpp&gt;
using namespace cv;
using namespace std;
using namespace gpu;[/php]

</span></div>