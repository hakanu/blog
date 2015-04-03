---
layout: post
title: OpenDNS Guide&#039;i engellemek
date: '2009-10-07 18:05:42'
---

Eğer bazı sebeplerle(!) DNS adresinizi değiştirdiyseniz ve opendns kullanıyorsanız ve de Firefox'ta arama çubuğunun(awesome bar) Google'in kendimi şanslı hissediyorum özelliğini kullanmasını seviyorsanız, muhtemelen opendns'e geçince bu sistem artık çalışmayacaktır. Direk siteye girmek yerine opendns guide diye bir arama sayfası açılmaktadır. Ayrıca sonuçları da Google'dan çok daha kalitesizdir. Bunu engelleyip tekrar eski haline döndürmek için şöyle bir şey yapabilirsiniz:

<strong><span style="color:#ff6600;"><em>Mozilla Firefox için:</em></span></strong>

- Firefox adres çubuğuna about:config yazılır

- "Söz veriyorum dikkatli olacağım" butonuna basılır

- Açılan sayfadaki arama kutusuna "keyword" yazılır

- Muhtemelen listede iki sonuç çıkacaktır. Şöyle bir görüntü olmalı:

<img class="aligncenter size-full wp-image-514" title="1" src="http://devdala.files.wordpress.com/2009/10/1.jpg" alt="1" width="692" height="144" />

- keywor.URL olana sağ tıklayıp "Değerini değiştir"e basılır ve yeni değer olarak şunları yazabilirsiniz:
<p style="padding-left:30px;">1) Eğer direk awesome bara yazılanın Google'da aranmasını isterseniz şunu yazın:</p>

<pre style="padding-left:30px;"><strong>http://www.google.com/search?q=<em>
</em></strong></pre>
<p style="padding-left:30px;">2) Ya da benim gibi "Kendimi şanslı hissediyorum"u kullanmak isteyenlerdenseniz:</p>

<pre style="padding-left:30px;"><strong>http://www.google.com/search?btnI=I%27m+Feeling+Lucky&amp;q=<em>

</em></strong></pre>
<strong><span style="color:#ff6600;"><em>Internet Explorer için:</em></span></strong>

<span style="color:#ff6600;"><span style="color:#000000;">- Başlat -&gt; Çalıştır yolu izlenerek çıkan pencereye "regedit" yazılır. Böylece kayıt defteri açılır</span></span>

<span style="color:#ff6600;"><span style="color:#000000;">- Şu kayda ulaşılır:</span></span>
<pre><strong>HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes
</strong></pre>
- Oradan şu değer açılır:
<pre><strong>{0633EE93-D776-472f-A0FF-E1416B8B2E3A}
</strong></pre>
- Yukarıdaki girdinin değeri aşağıdaki ile değiştirilir(Tabi Windows Live Search için):
<pre><strong>http://search.live.com/results.aspx?q={searchTerms}
</strong></pre>
- Eğer Google isterseniz o zaman girdi değerine şunu yazın:
<pre><strong>http://www.google.com/search?q={searchTerms}

</strong></pre>