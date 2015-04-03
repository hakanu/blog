---
layout: post
title: Kaybolan Onenote simgesini geri getirme
date: '2010-02-05 11:50:37'
---

<a href="http://www.hakanu.net/wp-content/uploads/2010/02/OneNote-icon.png"><img class="aligncenter size-full wp-image-872" title="OneNote-icon" src="http://www.hakanu.net/wp-content/uploads/2010/02/OneNote-icon.png" alt="" width="223" height="223" /></a>

Başlığın da çok ucu açık oldu. Microsoft Office Onenote programı ilk açıldığında system tray e Türkçe söylemek gerekirse sistem tepsisine bir simgesini atıyor. Bu simge sayesinde Win+N kombinasyonuyla hızlıca side note  yazılabiliyor ve kapatıldığında otomatik olarak Onenote'un istenilen kısmına kaydoluyor. Ayrıca screen clipping yaparken de baya kullanışlı Win+S'ye basıldığında anında istenen kısmın ekran görüntüsünü almayı sağlıyor. Bu simgenin belleğe yükü de az denecek kadar yok:) çok küçük miktarda bir ram tüketimi var. Yani sistem için sorun olmuyor.

Her şey iyi güzel de Office 2007 SP1 kurunca bu simge esrarengiz bir şekilde kaybolabiliyor. Ne yaptıysam geri getiremedim. Office'i silip tekrar kurdum SP1 de kurmadım üstüne yine olmadı. Ayarlarını değiştirdim yine fayda etmedi. Google beye başvurunca şöyle bir yöntem buldum:

- Yeni bir text dosyası oluşturun
- İçine şunları yazın
<ul></ul>
<p style="padding-left: 60px;">Office  versiyonuna göre 11.0 kısmını değiştirin. Bunu Program Files içindeki  Microsoft Office klasörünün içine bakarak öğrenebilirsiniz.</p>

<blockquote style="padding-left: 60px;">
<pre>Windows Registry Editor Version 5.00</pre>
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Office\11.0\OneNote]</pre>
<pre>"FirstBoot"= -</pre>
</blockquote>
<p style="padding-left: 60px;"></p>
<p style="padding-left: 60px;"><em><strong>Onenote  2007 kullananlar için şöyle olmalı:</strong></em></p>

<blockquote style="padding-left: 60px;">
<pre>Windows Registry Editor Version 5.00</pre>
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Office\12.0\OneNote]</pre>
<pre style="padding-left: 60px;">"FirstBoot"= -</pre>
</blockquote>
- Dosyayı      kaydedip kapattıktan sonra da adını      .reg uzantılı yapın. Adını ne koyduğunuzun bi önemi yok. ontray.reg      mesela.
- Bu ontray.reg dosyasına çift tıklayın ve çıkan uyarıya      evet diyip yeni kaydı kayıt defterine ekleyin.
- Bilgisayarı yeniden başlatın
- Onenote açın.
- Hala tepside simge görünmüyorsa Tools-Options-Other yolunu       izleyerek(Araçlar-Ayarlar-Diğer) bir ayar ekranına gelin. En üstteki       seçenekte tik olduğuna emin olun. Onenote simgesini göster tarzı bir       ayardır o. Tamam diyip kapatın. Simgenin gelmiş olması lazım artık
<ul></ul>
<p style="padding-left: 60px;">Bunlardan sonra hala gelmediyse şansınıza küsün. Windows 7'de bu yöntemi ben uygulayamadım. XP'de oldu ama.</p>