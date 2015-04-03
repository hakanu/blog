---
layout: post
title: OpenCV ile Nvidia Performance Primitives'in (NPP) beraber kullanılması
date: '2011-08-16 20:40:34'
---

<p style="text-align: center;"><a href="https://lh3.googleusercontent.com/-bIp9bwHy04Y/Tkq-oisKhBI/AAAAAAAAAv8/hUbmwN2RFGg/s1152/1.jpg"><img class="aligncenter" src="https://lh3.googleusercontent.com/-bIp9bwHy04Y/Tkq-oisKhBI/AAAAAAAAAv8/hUbmwN2RFGg/s1152/1.jpg" alt="" width="691" height="294" /></a></p>
Nvidia, <em>CUDA</em>'yı olabildiğince yüzüstü bırakmamaya çalışıyor. Ancak kötü reklam anlayışı yüzünden hala anlaşılamamış noktalar var. Mesela <em>Nvidia Performance Primitives</em> diye devasa bi kütüphane çıkardılar. Bunu ne duyan ne bilen var doğru dürüst. Neden? Çünkü dökümantasyon diye sadece fonksiyon prototipleri, parametre tipleri ve isimlendirme conventionlarını yazmışlar da ondan. Kapalı kutu gibi. Daldırdım elimi içine proje zamanı ben de. Uğraştım azcık. Azcık değil tabi baya baya. Çünkü bu kütüphanenin iddiası şudur image processing, video processing, signal processing işlemleri için arkadaki gpu fonksiyonlarını bilmeden üst düzey bir dille gpu'nun gücünü kullanmak. Bu alanda başka kütüphaneler de var elbet ki ben onların en ünlülerini incelemiştim. En kapsamlısı buydu içlerinde. Npp diyeceğim yazının devamında kısaca. Yalnız şöyle bir olayı var ki beni kahretmişti, 2 hafta bir fonksiyonunu çalıştırmak için uğraşmıştım -isim de veriyim utansın: <em>Canny edge detection</em>- çalışmadı bir türlü. Cuda 3.1de çalışıyordum o vakit, 3.2 çıktı sonra bi baktım bizim nppCanny fonksiyonu hiç bi yerde yok. Dökümantasyonu ara tara yok. Kütüphaneden çıkarmışlar meğer. Bugından dolayı. Neyse çok konuştum. Şimdi görüntü işlemeciler normalde Intel'in süpersonik bedava kütüphanesi OpenCV'yi kullanırlar. Bunun alışılageldik imaj tutma veri yapısı da IplImage'dir malumunuz. Ben madem gpu kullanacağım arada bir geçiş sağlamalıyım ki etkin olduğu yerde OpenCV'yi kullanırım, onun zayıf kaldığı yerde gpu'ya veririm işi o yapar çabukca. Evet çıkış noktam buydu. Bunun içinde bir interoperability-bu kelimeyi seviyorum- sağlamak gerekiyordu. memcpy kullanılacağını farketmiştim te o zaman. Ama bir hafta malolacağını hesap etmemiştim:) Nvidia Performance Primitives'in de kendine özgü çok güzel imaj tutma veri yapıları var.

Örneğin;

<code>
<pre lang="cpp" line="1">
npp::ImageCPU_8u_C1 oHostSrc;             //8 bitlik grayscale bir imaj tanımlanır. Bu bilgisayar belleğindeki resim için.
npp::loadImage(sFilename, oHostSrc);      //Diskten grayscale imaj okunur. Misal Lena.pgm çok müsait bu işe.
npp::ImageNPP_8u_C1 oDeviceSrc(oHostSrc); //Direk bilgisayar belleğindeki imajı kullanarak gpu belleğinde bir imaj oluşturulur.
</pre>
</code>

Muhteviyatında temel olarak Npp8u* var. Yani bir Npp8u lardan dizi. Peki Npp8u'nun özelliği ne. Yok bi özelliği. 8 bitlik unsigned char kendisi. #DEFINE ile böyle tanımlanmış kütüphanede. Peki OpenCV'nin legacy formatı IplImage'daki data alanının türü ne? Tabiyki char*. Bu bilgiyi akılda tutulmalı lazım olacak.

Aşağıya sıfırdan bir Visual Studio projesi yaratıp OpenCV 2.3 ve Cuda bağımlılıklarının eklenip opencv ve npp'nin nasıl beraber çalıştığını gösteren basit bir image mirror koydum. OpenCV diskten imajı okuyor. Grayscale'a çeviriyor. Arkasından ekran kartının belleğine fırlatıyor onu. O da grayscale imajı ters çevirip geri normal belleğe yolluyor. Teorinin pratikte acısız çalışması için imaj boyutları çok azami dikkatle verilmeli. Üzülmeyin sora.

<em>CUDA Toolkit Version: 4.0</em>

<em>OpenCV Version: 2.3</em>

1. Linker -&gt; General -&gt; Additional library directories:
<blockquote>
<pre>D:\fw\OpenCV2.3\opencv\lib\Debug;
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v4.0\lib\Win32</pre>
</blockquote>
<p style="text-align: center;"><a href="https://lh5.googleusercontent.com/-7yPfHXJjIoI/TkrM0Aa2jgI/AAAAAAAAAwE/y91JDEqB6JQ/2.jpg"><img class="aligncenter" src="https://lh5.googleusercontent.com/-7yPfHXJjIoI/TkrM0Aa2jgI/AAAAAAAAAwE/y91JDEqB6JQ/2.jpg" alt="" width="600" height="270" /></a></p>
-------------------------------------------------------------------------------------------------------------------------

2. Linker -&gt; Input -&gt; Additional Dependencies
<blockquote>
<pre>opencv_calib3d230d.lib
opencv_contrib230d.lib
opencv_core230d.lib
opencv_features2d230d.lib
opencv_flann230d.lib
opencv_gpu230d.lib
opencv_haartraining_engined.lib
opencv_highgui230d.lib
opencv_imgproc230d.lib
opencv_legacy230d.lib
opencv_ml230d.lib
opencv_objdetect230d.lib
opencv_video230d.lib
cublas.lib
cuda.lib
cudart.lib
cufft.lib
curand.lib
cusparse.lib
npp.lib
nvcuvenc.lib
nvcuvid.lib
OpenCL.lib</pre>
</blockquote>
<p style="text-align: center;"><a href="https://lh6.googleusercontent.com/-WTaf5iXkLwk/TkrM0yX8gsI/AAAAAAAAAwI/EHA2-Jn-40A/3.jpg"><img class="aligncenter" src="https://lh6.googleusercontent.com/-WTaf5iXkLwk/TkrM0yX8gsI/AAAAAAAAAwI/EHA2-Jn-40A/3.jpg" alt="" width="599" height="515" /></a></p>
-------------------------------------------------------------------------------------------------------------------------

3. Additional Include Directories:
<blockquote>
<pre>D:\fw\OpenCV2.3\build\include;
D:\fw\OpenCV2.3\build\include\opencv;
D:\fw\OpenCV2.3\build\include\opencv2;
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v4.0\include</pre>
</blockquote>
<p style="text-align: center;"><a href="https://lh6.googleusercontent.com/-bLaRugkIURM/TkrM2FMvzMI/AAAAAAAAAwM/ipplyPPlOWY/4.jpg"><img class="aligncenter" src="https://lh6.googleusercontent.com/-bLaRugkIURM/TkrM2FMvzMI/AAAAAAAAAwM/ipplyPPlOWY/4.jpg" alt="" width="602" height="198" /></a></p>
---------------------------------------------------------------------------------------------

4. Kod:

<code>
<pre lang="cpp" line="1">
//Temel headerlar
#include "iostream"
#include <stdio.h>

//opencv headerları
#include <highgui.h>
#include <cv.h>
#include <cxcore.h>

//npp headeri
#include <npp.h>		//tek header olayı süper olmuş

using namespace std;

//Prototypes
int nppImageMirror();

//main func
int main()
{
	cout << "basladi" << endl;

	nppImageMirror();

	cout << "bitti" << endl;
	getchar();
	return 0;
}

//npp-opencv func
int nppImageMirror()
{

	//
	// OPENCV KISMI
	//
	printf("OpenCV kismi basliyor\n");

	IplImage* img = cvLoadImage( "c:/temp/rachel.jpg",1 );

	Npp8u * frame_C;
	Npp8u * result_C;
	int new_pitch, res_pitch;

	frame_C = nppiMalloc_8u_C1(img->width, img->height, &new_pitch);
	result_C = nppiMalloc_8u_C1(img->width, img->height, &res_pitch);

	int width = img->width, height = img->height;

	CvSize frame_size = cvSize(img->width, img->height);
	IplImage *gray = cvCreateImage(frame_size, IPL_DEPTH_8U, 1);
	IplImage *result = cvCreateImage(frame_size, IPL_DEPTH_8U, 1);

	NppiSize size;
	size.height = img->height;
	size.width = img->width;
	cvCvtColor(img, gray, CV_BGR2GRAY);		//Imajı grayscale a çevir

	cudaMemcpy2D(frame_C, new_pitch, gray->imageData, gray->widthStep, width*gray->nChannels, height, cudaMemcpyHostToDevice);
	nppiMirror_8u_C1R(frame_C, new_pitch, result_C, res_pitch, size, NPP_HORIZONTAL_AXIS);//mirror fonksiyonu
	cudaMemcpy2D(result->imageData, result->widthStep,  result_C, res_pitch, width*result->nChannels, height, cudaMemcpyDeviceToHost);

	/////TERS CEVİRME KISMI BİTTİ

	cvNamedWindow("Input", CV_WINDOW_AUTOSIZE);
	cvNamedWindow("Result", CV_WINDOW_AUTOSIZE);
	cvShowImage("Input", img);
	cvShowImage("Result", result);

	cvWaitKey(0);		//Esc bekle

	//Free kısmı bu da -- önemli gayet
	cvReleaseImage( &img );
	cvReleaseImage( &gray );
	cvReleaseImage( &result );
	cvDestroyWindow("Input");
	cvDestroyWindow("Result");
	nppiFree(frame_C);
	nppiFree(result_C);

    return 0;
}
</pre>
</code>

5. Program çıktısı:
<p style="text-align: center;"><a href="https://lh5.googleusercontent.com/-VDR5zxWVUfg/TkrM26gnsKI/AAAAAAAAAwQ/JKDWoz3elJw/s1152/5.jpg"><img class="aligncenter" src="https://lh5.googleusercontent.com/-VDR5zxWVUfg/TkrM26gnsKI/AAAAAAAAAwQ/JKDWoz3elJw/s1152/5.jpg" alt="" width="645" height="332" /></a></p>

<h2>Derinlemesine</h2>
Resmin diskten okunması (1:Renkli okur, 0:Grayscale okur):

<code>
<pre lang="cpp" line="1">IplImage* img = cvLoadImage( "c:/temp/rachel.jpg",1 );
</pre>
</code>

Resme ekran kartı belleğinde yer alınması:

<code>
<pre lang="cpp" line="1">
frame_C = nppiMalloc_8u_C1(img->width, img->height, &new_pitch);
</pre>
</code>

Resmin griye çevrilmesi:

<code>
<pre lang="cpp" line="1">
cvCvtColor(img, gray, CV_BGR2GRAY);
</pre>
</code>

Resmin bilgisayar belleğinden ekran kartı belleğine kopyalanması:

<code>
<pre lang="cpp" line="1">
cudaMemcpy2D(frame_C, new_pitch, gray->imageData, gray->widthStep, width*gray->nChannels, height, cudaMemcpyHostToDevice);
</pre>
</code>

Resmin ekran kartında aynalanması -ben uydurdum kelimeyi şu anda-(Son parametreyle yatay, dikey değiştirilebilir):

<code>
<pre lang="cpp" line="1">
nppiMirror_8u_C1R(frame_C, new_pitch, result_C, res_pitch, size, NPP_HORIZONTAL_AXIS);
</pre>
</code>

Resmin ekran kartı belleğinden bilgisayar belleğine kopyalanması:

<code>
<pre lang="cpp" line="1">
cudaMemcpy2D(result->imageData, result->widthStep,  result_C, res_pitch, width*result->nChannels, height, cudaMemcpyDeviceToHost);
</pre>
</code>

Projeye kodları ile şurdan ulaşılabilir (Visual Studio 2010)
<a href="http://dl.dropbox.com/u/3600380/Projeler/Blog/ComputerVision/NppOpencvOrnek1.zip" target="_blank">OpenCv-Npp Sample Project</a>