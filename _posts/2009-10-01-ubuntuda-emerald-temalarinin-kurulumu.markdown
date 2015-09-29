---
layout: post
title: Ubuntu&#039;da Emerald temalarının kurulumu
date: '2009-10-01 22:12:56'
---

<img class="aligncenter size-full wp-image-418" title="emerald" src="http://devdala.files.wordpress.com/2009/10/emerald.png" alt="emerald" width="118" height="118" />

Ubuntu'nun görselliğine hasta olan arkadaşlara armağan ettiğim bu yazıda bir işletim sisteminin nasıl büssürü farklı kılığa bürünebileceğini göreceksiniz. Emerald denilen uygulama temelde bir window decorator dır. Halihazırda yeni bir Ubuntu sürümü kullanıyorsanız pencere efekti yöneticiniz compiz dir. Her ne kadar compiz güzel olsa da emerald ile başka başka birçok temayı bilgisayarımıza kurabiliriz. Bunun için öncelikle Emerald Theme Manager'i bilgisayara kurmak gerekir. Sistem -&gt; Yönetim -&gt; Synaptic Paket Yöneticisi yolunu izleyerek Synaptic'i açıyoruz ve arama çubuğuna emerald yazıyoruz. Açıklamasında "Decorator for compiz-fusion" yazan adı "emerald" olan pakedi işaretleyip bilgisayara kurulmasını sağlıyoruz. İşlem bitince Sistem -&gt; Yönetim yolu izlendiğinde çıkan menüde "Emerald Theme Manager" görünecektir. Açılıp "import" butonuna basılarak emerald temaları kolayca kurulabilir. Yalnız burada önemli olan nokta temalar import edilip hemen kullanılamaz window decorator'imizi Compiz'den Emerald'a çevirmemiz gerekir bunun için Alt+F2 tuşlarına basıyor ve şunu yazıyoruz:
<pre>emerald --replace</pre>
Emerald'den sıkılırsanız Compiz'i geri getirmek için de Alt+F2'ye basıp şunu yazmanız yeterli:
<pre>compiz --replace
</pre>
Çok şık emerald ve compiz temaları indirmek için:

<a href="http://www.gnome-look.org">http://www.gnome-look.org</a>

<a href="http://compiz-themes.org">http://compiz-themes.org</a>