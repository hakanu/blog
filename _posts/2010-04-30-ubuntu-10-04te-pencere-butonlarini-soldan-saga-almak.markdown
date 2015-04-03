---
layout: post
title: Ubuntu 10.04'te pencere butonlarını soldan sağa almak
date: '2010-04-30 16:00:39'
---

10.04'ü kurdum bismillah demeden pencere kapatma tuşunu bulamadım. Mac stili sağa almışlar. Hangi temaya geçersem geçiyim böyle. Düzeltme yöntemi ise şöyle:

- Terminali açıp "gconf-editor" yazarak gconf-editor ü açıyoruz.

- apps-&gt;metacity-&gt;general yolunu izliyoruz ve ordan change button_layout value to <strong>:maximize,minimize,close </strong>şeklinde değiştiriyoruz. Bu pencere butonlarının diziliş sırasını  ayarlar normalde.

- Pencere başlığını ortaya almak isterseniz ki zaten ortadaysa yapmanıza gerek yok şunu yapıyoruz:
<blockquote><strong>sudo nano /usr/share/themes/Ambiance/metacity-1/metacity-theme-1.xml</strong></blockquote>
- <strong>&lt;!-- Window Title --&gt; </strong>kısmını bulun ve orayı şöyle değiştirin(yedeğini alın da sonra bana kızmayın bişi olur molur):
<pre dir="ltr">&lt;!-- Window Title --&gt;

&lt;draw_ops name="draw_title_text_normal"&gt;
  &lt;title color="#dfd8c8"
         x="(width - title_width) / 2"
         y="(((height - title_height) / 2) `max` 0)"/&gt;

&lt;/draw_ops&gt;

&lt;draw_ops name="draw_title_text_inactive"&gt;
  &lt;title color="#99958b"
         x="(width - title_width) / 2"
         y="(((height - title_height) / 2) `max` 0)"/&gt;
&lt;/draw_ops&gt;</pre>
NOT: Bunlarla hiç uğraşmam diyenler için şurda ambience temasının editlenmiş hali var. Bunu kurarsanız butonlar otomatik olarak soldan sağa geçer.

<a href="http://dl.dropbox.com/u/3600380/Ambiance2.tar.gz" target="_self">Download edited ambience theme</a>