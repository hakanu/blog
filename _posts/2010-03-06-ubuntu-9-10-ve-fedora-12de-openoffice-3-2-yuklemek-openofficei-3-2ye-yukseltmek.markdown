---
layout: post
title: Ubuntu 9.10 ve Fedora 12'de OpenOffice 3.2 yüklemek, OpenOffice'i 3.2'ye yükseltmek
date: '2010-03-06 20:55:06'
---

<a href="http://www.hakanu.net/wp-content/uploads/2010/03/openoffice-3.png"><img class="aligncenter size-full wp-image-960" title="openoffice 3" src="http://www.hakanu.net/wp-content/uploads/2010/03/openoffice-3.png" alt="" width="286" height="214" /></a>

Neyse ki post başlıklarına karakter sınırı yok. Sözlüklerdeki gibi sınırlandırılmıyoruız. Malumunuz Openoffice'in yeni versiyonu çıktı. Linux altındaki en güçlü ofis yazılımı da bu olduğundan ve 3.2 versiyonunun da çok hızlı olduğundan bahsedilince insan yükseltmek istiyor haliyle. Lakin Ubuntu 9.10'da gelen sürüm 3.1.1. Hadi gelin hep beraber 3.2'ye geçelim oldukça basit oley.

1) Öncelikle şurdan kendinize uygun OpenOffice versiyonunu indirin hadi bakiyim(Synaptic'ten kurarım derseniz indirmeyin kotalıysanız falan):

<a href="http://download.openoffice.org/other.html" target="_blank">Download OpenOffice 3.2 package</a>

2) İndirdin mi tamam home klasörünün altına atabilirsin. Ya da yolunu bildiğin bi yere at. Kullanıciz bu bilgiyi

3) İlk yöntemimiz Synaptic'e yeni depo ekleyip ordan çekmek. PPA denilen paketler sayesinde synaptic paket yöneticisi ne yazılımların güncel versiyonları eklenebilir. Tabi henüz resmi olmadan. Biz de OpenOffice'inkini ekliyoruz. Şu şekilde:
<pre><strong><strong>sudo add-apt-repository <strong>ppa:openoffice-pkgs/ppa
</strong></strong></strong></pre>
Depo ekleme işleminden sonra mecbur bunu da yapmalı:
<pre>
<pre><strong>sudo apt-get update &amp;&amp; sudo apt-get upgrade
</strong></pre>
</pre>
<strong> </strong>

4) Burdan sonra direk kurabilirsiniz. Ben diğer yöntemi kullandım. Bunu denedim. Açıkçası el yordamıyla yaptım olmadı. Alttaki daha garanti.

<span style="text-decoration: underline;">OpenOffice 3.2 kurulumu(diğer yöntem):</span>

1) Öncelikle OpenOffice namına ne varsa bilgisayardan siliyoruz. Buyrun ki:
<pre><strong>sudo apt-get remove openoffice*.*</strong></pre>
2) Oh silindi. Şimdi yukarıda OpenOffice.org'dan kendimize uygun olarak indirdiğimiz OpenOffice debian pakedini arşiv yöneticisiyle açmalıyız. Bunun için indirdiğimiz pakedin bulunduğu konuma terminali açıp cd komutlarıyla ulaşmalıyız. Ama dediğim gibi direk home klasörüne attıysanız hiç gereği yok. Doğrudan aşağıdaki kodu yazabilirsiniz.
<pre><strong>tar xzvf OOo_3.2.0_LinuxIntel_install_en-US_deb.tar.gz</strong></pre>
Not: Küçüğünden bi not. Üstteki komutu indirdiğiniz versiyona göre yazın. Misal bu versiyon Ameriken İngilizcesi olanı. İngiliz İngilizce si olanda GB yazıyor falan. Büyük britanya ya hani ordan. İndirdiğiniz dosyanın adına göre yani. Ezberden yapmayın.

3) Arşiv açıldıktan sonra açılan klasörün içine  cd komutuyla girilir. Dediğim gibi yine dosya ismine göre girin siz. Bendeki şöyleydi:
<pre><strong>cd OOO320_m12_native_packed-1_en-US.9483/</strong></pre>
4) Yazılımı yüklemek için şu komutu veriyoruz:
<pre><strong><strong>sudo dpkg -iR DEBS/</strong></strong></pre>
5) Bi paket silmek içinse şu komutu vermeli:
<pre><strong><strong>sudo dpkg -r openoffice.org</strong></strong></pre>
6) Bilgisayarı yeniden başlatın.

<span style="text-decoration: underline;">RPM tabanlı sistemlerde OpenOffice 3.2 kurulumu ve yükseltimi(Redhat, Fedora, Centos)</span>

1) Yükleme yapmak için root olunur. Superuser diyen de var.
<pre><strong><strong>su -</strong></strong></pre>
2) İndirilen paket açılır. Üstteki gibi.
<pre><strong>tar -xvf OOo_3.2.0_xxxxxxxx_LinuxIntel_install_wJRE_en-US.tar.gz</strong></pre>
3) cd komutuyla açılan klasörün içine girilir.
<pre><strong>cd 000320_xx_native_packed-1_en-US.9476</strong></pre>
4) Güvenlik bilmemnesi sebebiyle şunu yapmak gerekiyormuş.
<pre><strong><strong>XAUTHORITY=/home/{username}/.Xauthority; export XAUTHORITY
DISPLAY=:0.0; export DISPLAY</strong></strong></pre>
5) Kurulum dosyasını başlatıp yönergeleri izleyin
<pre><strong><strong>./setup</strong></strong></pre>
6) Kurulum tamamlandıktan sonra superuser kabugunu terkedin. Nolur nolmaz:
<pre><strong><strong>exit</strong></strong></pre>
6) Bilgisayarı yeniden başlatın.

Hakan UYSAL(kendi sitemden kendi siteme reklam vercem. Botlar her yerde engelleyemiyoruz efendim)

<a href="http://www.hakanu.net/" target="_blank">www.hakanu.net</a>