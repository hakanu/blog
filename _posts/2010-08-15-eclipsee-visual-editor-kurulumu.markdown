---
layout: post
title: Eclipse'e Visual Editor kurulumu
date: '2010-08-15 12:02:38'
---

Bilindiği üzre Eclipse'te dahili bi GUI builder yok. Ama büssürü gui plugini var. En methedileni de Visual Editor. Haydi bunu kuralım.

1) Öncelikle Eclipse 3.5.x versiyonunu indiriyoruz. Helios(3.6) versiyonuna bu plugin kurulamıyor. Neden bilmiyorum emf'ten falan sorun çıkarıyor olabilir. Neyse şurdan indirelim Galileo'yu-tabi size uygun olanını. Misal Eclipse IDE for Java EE Developers olabilir-:

<a href="http://www.eclipse.org/downloads/packages/release/galileo/r" target="_blank">Download Eclipse Galileo</a>

2) Eclipse'i açtıktan sonra Help -&gt;  Install New Software diyoruz.

3) "Work with" kısmına aşağıdaki adresi yazıyoruz ve alt panelde "Pending" yazısının geçmesini bekliyoruz
<blockquote>
<pre>http://download.eclipse.org/tools/ve/updates/1.4/</pre>
</blockquote>
4) "Pending" kısmı geçince kurulacak pluginin dosyaları görünecek hepsini seçiyoruz. "Finish" diyoruz.

5) Eclipse'i yeniden başlatınca artık JFrame JApplet gibi seçenekler yeni proje kısmına dahil olacak. Drag drop gui yapabilmenize imkan sağlanacak.

Notnot: Beğenmeyenlere Jigloo Gui Builder'i da tavsiye edebilirim.