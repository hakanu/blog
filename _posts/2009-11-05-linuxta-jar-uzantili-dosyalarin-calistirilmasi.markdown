---
layout: post
title: Linux&#039;ta jar uzantılı dosyaların çalıştırılması
date: '2009-11-05 20:45:44'
---

<strong>.jar uzantılı java uygulamaları genelde varsayılan Linux sürümlerinde çift tıklayarak çalıştırılamaz, sıkıştırılmış arşiv gibi davranır. Eğer bunlar çalıştırılabilir(executable) bir uygulama ise çalıştırmak için sırayla şunlar yapılır.</strong>

<strong>1.Terminal(Uçbirim) açılır.
</strong>

<strong>2. cd komutlarıyla jar uzantılı dosyanın bulunduğu klasöre gidilir.</strong>

<strong>3. Şu kod yazılarak çalıştırma işlemi yapılır:</strong>
<pre><strong><em>java -jar &lt;dosya_ismi&gt;.jar</em>
</strong></pre>
<strong>Gayet kolay evde deneyebilirsiniz. Eğer uygulamaya parametre geçiliyorsa yine buradan yapılabilir. Mesela iki tane text dosyasını parametre olarak alan jar uygulamasının Linux ortamında çalıştırılması için:</strong>
<pre><strong><em><strong><em>java -jar &lt;dosya_ismi&gt;.jar parametre1.txt parametre2.txt

</em></strong></em></strong></pre>