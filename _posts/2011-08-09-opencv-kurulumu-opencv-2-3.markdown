---
layout: post
title: Opencv kurulumu - Opencv 2.3
date: '2011-08-09 20:54:58'
---

<a href="http://devdala.files.wordpress.com/2011/08/bscap04571.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/bscap04571.jpg" alt="" width="645" height="363" /></a>

Şimdi CUDA desteği olmadan kurulumun nasıl olduğunu klavyem döndüğünce anlaticim. Fazla bişisi yok zaten.
<ol type="1">
	<li value="1">Opencv indir</li>
</ol>
<a href="http://sourceforge.net/projects/opencvlibrary/">http://sourceforge.net/projects/opencvlibrary/</a>

Superpack'i kurdum.
<ol type="1">
	<li value="2">Visual Studio açılır. Yeni Console application C++ projesi oluşturulur.</li>
	<li>Projenin Properties'ine gelinir ve C/C++ -&gt; General -&gt; Additional Include Directories'e şunlar eklenir(sizin opencv nereye kuruluysa işte):</li>
</ol>
<blockquote>
<pre>D:\fw\OpenCV2.3\build\include
D:\fw\OpenCV2.3\build\include\opencv
D:\fw\OpenCV2.3\build\include\opencv2</pre>
</blockquote>
<a href="http://devdala.files.wordpress.com/2011/08/opencv-11.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-11.png" alt="" width="752" height="303" /></a>

Opencv2 yeni gelen headerlar için. 2.1den 2.2ye geçişte böyle bi değişikliğe gidildi. Compatibilityden ödün vermeyelim diye de böyle bişi yaptılar. Bizde 2.3 olduğu için yine aynı geleneğin devam ettiği görülüyor.

4. Linker -&gt; Input'a geliyoruz. Şunları ekliyoruz. (Aslında bunların hepsini eklemeye gerek yok. Sadece kullanacağımızı yazsak yeterli. Ben ilerki büyük projeler için de yazdım. )
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
opencv_ts230d.lib
opencv_video230d.lib</pre>
</blockquote>
<a href="http://devdala.files.wordpress.com/2011/08/opencv-21.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-21.png" alt="" width="747" height="303" /></a>

<a href="http://devdala.files.wordpress.com/2011/08/opencv-31.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-31.png" alt="" width="750" height="428" /></a>

Deneme kodu:

<code>
<pre lang="c" line="1">
#include <stdio.h>
#include <highgui.h>
int main( int argc, char** argv )
{
	printf("basladi\n");
	IplImage* img = cvLoadImage( "D:\\Temp\\marion.jpg",1 );
	cvNamedWindow("Monas", CV_WINDOW_AUTOSIZE );
	cvShowImage("Monas", img );
	cvWaitKey(0);
	cvReleaseImage( &img );
	cvDestroyWindow("Monas");
	printf("bitti\n");
	getchar();
	return 0;

}
</pre>
</code>

Poroğramımın çıktısı: (marion'a selamlar)

<a href="http://devdala.files.wordpress.com/2011/08/opencv-81.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-81.png" alt="" width="676" height="400" /></a>

5. Ortam değişkenlerine opencv kütüphanesinin bin klasörünün yolu gösterilir ki dll dosyalarını derlediğimiz exe görsün. Bu olayın ayrıntılı açıklamasını okumak isteyenler şu tarafa gitti: <a href="http://www.hakanu.net/?p=1619">http://www.hakanu.net/?p=1619</a>

Neyse şöyle yapıyoruz ortam değişkenleri olayını (environment variables):

<a href="http://devdala.files.wordpress.com/2011/08/opencv-51.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-51.png" alt="" width="378" height="418" /></a>

<a href="http://devdala.files.wordpress.com/2011/08/opencv-6.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/opencv-6.png" alt="" width="345" height="126" /></a>

İşletim sistemim windows 7 yanlış anlaşılmasın:p

Sıradaki post Cuda desteği ile Opencv 2.3ü derlemek ve kullanmak olcak. Stay tuned fellas T_T