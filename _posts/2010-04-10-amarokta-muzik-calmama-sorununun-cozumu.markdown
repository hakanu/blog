---
layout: post
title: Amarok'ta müzik çalmama sorununun çözümü
date: '2010-04-10 22:35:18'
---

Böyle çift tıklıyorsun şarkıya çalmıyor. Hızlıca ilerliyor bar şarkı bitti diyor. Çözümü gayet basit:

1) Hemencecik terminali açıyoruz ve şunu yazıyoruz:
<blockquote><em>sudo apt-get install kubuntu-restricted-extras</em></blockquote>
2) Bu yüklenecek. Eğer ki bilgisayarınızda jdk kurulu değilse onu da indirecek. Biraz zaman alabilir. Sakin olun. Ardından şunu kuruyoruz -büyük ihtimal bu sizde zaten kuruludur da garanti olsun bizim işimiz-
<blockquote><em>sudo apt-get install libxine1-ffmpeg</em></blockquote>