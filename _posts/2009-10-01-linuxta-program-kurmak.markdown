---
layout: post
title: Linux&#039;ta program kurmak
date: '2009-10-01 19:27:43'
---

Uzun süredir Linux kullanan ileri düzey kullanıcılar için olmasa da bu yola yeni baş koymuş arkadaşlara yardımcı olabilecek bir yöntemdir.

Linux'ta program kurmanın çeşitli yolları vardır. Bu yollardan kimisi ciddi bir eziyetken kimisi oldukça basittir. Tabi kurmak istediğiniz programa bağlı.

İlk yöntem Synaptic Paket Yöneticisi'ni kullanmaktır. Bunu Sistem -&gt; Yönetim -&gt; Synaptic Paket Yöneticisi yolunu kullanarak açabilirsiniz. Arama çubuğuna istediğiniz programı yazıp çıkan listeden işaretleyip "Uygula" butonuna basmanız yeterlidir. Böylece işletim sistemi kendi deposundan programı indirip bilgisayara otomatik yükler.

Diğer yöntem ise terminal kullanarak yüklemedir. Bunun için Uygulamalar -&gt; Donatılar -&gt; Uçbirim yolu izlenerek Terminal açılır ve indirme kodu yazılır. İndirme kodu şu şekildedir:
<pre>sudo apt-get install xxx
</pre>
<em>sudo:</em> Size root(yönetici) haklarını verir

<em>apt-get:</em> Debian paket yöneticisine bağlanmak içindir

<em>install:</em> Yüklemek demektir

<em>xxx:</em> İstediğiniz programın adıdır.

Örneğin Opera web tarayıcısını kurmak için:
<pre>sudo apt-get install opera
</pre>
yazıp entera basmak yeterlidir.

Küçük bir not Synaptic Paket Yöneticisi  ile program kurarken  aynı zamanda terminalden de program kurmaya çalışmayın hata verecektir. Aynı anda tek bir installer çalışabilir. Bu sistem Windows'ta da vardır. Aynı anda iki tane windows installer açamazsınız.

Bir diğer yöntem ise tar.gz ve benzeri uzantılı program kurulum dosyasını indirip kurmadır ki en gıcık olanı budur. Bunun için belli bir kurulum şekli yoktur. tar.gz paketinin içinden çıkan setup.txt tarzı belge okunmalıdır. Onun içinde programa özel kurulum şekli anlatılır genelde.