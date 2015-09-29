---
layout: post
title: .bin uzantılı dosyaları kurmak
date: '2010-06-04 20:25:07'
---

Ubuntu veya türevleri Linux dağıtımlarında .bin uzantılı setup dosyalarını çalıştırmak için şunları yapıyoruz:

1) Terminal açılıp şu komut yazılır.
<blockquote>
<pre dir="ltr">chmod a+x dosya_adi.bin</pre>
</blockquote>
2) Üstteki kod ile dosyaya gerekli izinleri vermiş olduk. Şimdi bildiğimiz executable file çalıştırır gibi çalıştırıyoruz.
<blockquote>
<pre dir="ltr">./dosya_adi.bin</pre>
</blockquote>
Not: Eğer izniniz yok diyip kuruluma izin vermezse şöyle yapılıp root haklarıyla kurulum yapılabilir:
<pre dir="ltr">
<blockquote>
<pre dir="ltr">sudo ./dosya_adi.bin</pre>
</blockquote>
</pre>