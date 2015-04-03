---
layout: post
title: Ubuntu'ya font yüklemek
date: '2010-04-21 10:33:09'
---

Windows'ta bulunan yazı tiplerinden kopamayan biriyseniz, bunları Ubuntu'ya kurmak istiyorsanız ya da istemiyorsanız her neyse şöyle yapıyoruz:

1) Ubuntu'da fontlar şurda tutuluyor:
<blockquote>
<pre><strong>/usr/share/fonts/</strong></pre>
</blockquote>
2) Tabi buraya yazma/okuma konusunda pek şansınız yok. Onun için hemencecik bir hileyle bu klasörü root olarak açıyoruz. Onun büssürü yöntemi var. Şunu yapabilirsiniz mesela alt-f2 kombinasyonuyla "Uygulama Çalıştırıcı"yı açıp oraya şunu yazıp root olarak klasörü açabilirsiniz:
<blockquote>
<pre><strong>gksudo nautilus /usr/share/fonts/</strong></pre>
</blockquote>
3) Buraya font yükleyebilirsiniz. Eğer ki yükleyeceğiniz font truetype ise ki Windows fontları böyledir "truetype" isimli bir klasör açmanız gerekir. Güncel bir Ubuntu sürümü kullanıyorsanız bu klasör zaten mevcuttur. Yeni ekleyeceğiniz yazı tipleri doğrudan içine kopyalayarak kullanabilirsiniz.

Not: Genel Windows fontlarını kurmak için doğrudan şu komutu kullanabilirsiniz(Notun notu: Ubuntu 9.10'da bu kurulu geliyor zaten)
<blockquote>
<pre><strong>sudo apt-get install msttcorefonts</strong></pre>
</blockquote>