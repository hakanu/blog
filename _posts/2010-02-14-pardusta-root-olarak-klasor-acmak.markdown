---
layout: post
title: Pardus'ta root olarak klasör açmak
date: '2010-02-14 13:53:16'
---

Hayır sanki hepimiz Linux adminiymişiz gibi anlatıyorlar internette her şeyi. Değiliz, değilim. Tane tane anlatın şunları da öğrenelim ama diymi. Mesela root olamamıştım bi türlü Pardus'ta. Hani Ubuntu'da yine az çok biliyorum da Pardus KDE falan değişik. Bu normal bir Linux kullanıcısı için kolay bir iş olsa da yeni başlayan arkadaşlara yardımcı olur herhalde.

Neyse gayet kolay bir şekilde root olarak istediğiniz klasörü açıp üstünde oynayabilirsiniz. Şu adımları izleyiniz:

1) Alt+F2 tuş kombinasyonuyla program başlatıcıyı açıyoruz ki bu Ubuntu'tu da böyleydi. Buraya şunu yazıyoruz(Burada /usr klasörünün açılacağı varsayılmıştır. Siz kendinize göre değiştirebilirsiniz):
<pre>kdesu konqueror /usr
</pre>
<a href="http://www.hakanu.net/wp-content/uploads/2010/02/11.png"><img class="aligncenter size-full wp-image-917" title="1" src="http://www.hakanu.net/wp-content/uploads/2010/02/11.png" alt="" width="339" height="223" /></a>

2) Şifre sorma authentication ekranı gelecek. Şifrenizi girin.

<a href="http://www.hakanu.net/wp-content/uploads/2010/02/21.png"><img class="aligncenter size-full wp-image-918" title="2" src="http://www.hakanu.net/wp-content/uploads/2010/02/21.png" alt="" width="326" height="201" /></a>3) Tadaa bu maddede bişi yok. Açılmış olması lazım artık.

İkinci bir yöntem de terminalden(uçbirim) root olarak açma hadisesi. Onun için de şu kodu yazınız terminale:
<pre>su root</pre>
Ardından parolanızı girince terminal renklenecek hah işte root oldunuz. cd ile gezebilirsiniz dosyalar arasında ve istediğiniz işlemleri yapabilirsiniz.

<a href="http://www.hakanu.net/wp-content/uploads/2010/02/3.png"><img class="aligncenter size-full wp-image-919" title="3" src="http://www.hakanu.net/wp-content/uploads/2010/02/3.png" alt="" width="297" height="85" /></a>