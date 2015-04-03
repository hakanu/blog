---
layout: post
title: OpenCV'de fare tıklama olaylarını kontrol etmek
date: '2011-04-22 13:09:16'
---

OpenCV'de highgui ile gösterilen resmin herhangi bir noktasına fare ile basıldığında bunu kontrol etmek ve hatta bölgenin koordinatını yazdırmak için:

[c]

void on_mouse( int event, int x, int y, int flags, void* param )
{
 if ( event == CV_EVENT_LBUTTONDOWN )
 printf(&quot;%i %i\n&quot;, x, y);
}

void OpencvProcess::resimGoster(IplImage* par_img)
{
 cvNamedWindow(&quot;Monas&quot;, CV_WINDOW_AUTOSIZE );
 cvSetMouseCallback( &quot;Monas&quot;, on_mouse, NULL );
 cvShowImage(&quot;Monas&quot;, par_img );
 printf(&quot;resim gosteriliyor\n&quot;);
 cvWaitKey(0);
 cvDestroyWindow(&quot;Monas&quot;);
}

[/c]</pre>
Burda dikkat edilmesi gereken nokta on_mouse fonksiyonunun class a dahil edilmemiş olduğudur. cvSetMouseCallBack'te NULL olan parametre yerine de bir parametre geçilebilir. Hatta resim parametre verilerek on_mouse'ta onun üzerinde işlemler yapılabilir.