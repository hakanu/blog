---
layout: post
title: Photoshop'ta GPU desteğini etkin kılmak
date: '2010-05-28 08:32:05'
---

Adobe'nin CS4 ve CS5'e koyduğu bir özellik. İşlemciyi fazlasıyla yoran image processing işlemlerinde arkaya GPU'nun desteğini alıp daha pürüzsüz çalışma ortamı sağlıyor. Yapmak için şöyle:

1) Üst sekmelerden Edit'e geliyoruz. Ordan Edit -&gt; Preferences -&gt; Performance
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/05/12.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/05/12.jpg" alt="" width="371" height="570" /></a></p>
2) Açılan panelden "Enable OpenGL Drawing"in checkboxını işaretliyoruz. OK diyip kapatıyoruz bitti bu kadar. Denemek için bi resim atıp zoom yapabilirsiniz. Artık zoomlanmış hal görüntülenirken ekran yenilenmeyecek direk smooth zoom yapılacak.

<a href="http://devdala.files.wordpress.com/2010/05/22.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/05/22.jpg" alt="" width="208" height="166" /></a>

Ufak not: Tabi ekran kartınızın bu hadiseyi desteklemesi lazım. Çok çok eski olmadığı sürece destek veriyor. Benim emektar 8600 bile destek veriyor hesap et işte.