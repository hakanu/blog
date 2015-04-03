---
layout: post
title: Ubuntu ve XP kurulu bilgisayarda XP&#039;nin otomatik açılmasını sağlamak
date: '2009-08-30 14:59:15'
---

Microsoft Windows XP kurulu bilgisayara Ubuntu kurulursa, Ubuntu kurulumun ardından kendi boot yönetici programını yükler ve varsayılan olarak kendisini gösterir. Böylece bilgisayar açılırken 10 saniyelik bir "Hangi işletim sistemini" açayım ekranı çıkar ve kullanıcı tepki vermezse doğrudan Ubuntu açılır. Bu Kubuntu ve Xubuntu için de geçerlidir. Eğer kullanıcı Linux'u nadiren ama XP'yi sürekli kullanıyorsa bu işkenceye dönüşür. Bu nedenle varsayılan işletim sistemi ayarını değiştirmek için Ubuntu'da oturumum açıkken şunlar yapılmalıdır:
<ol>
	<li>Terminal(Uçbirim) açılır</li>
	<li><em><strong>sudo cp /boot/grub/menu.lst /boot/grub/menu.lst_backup</strong></em> kodu boşluklara dikkat edilerek terminalde yazılıp entera basılır. Böylece eski varsayılan ayarlar herhangi bir sebepten dolayı onlara dönülmek istenirse diye kopyalanır.</li>
	<li>Bize lazım olan dosya menu.lst dir. Bunun için bu dosyayı bir text editor'de açıp birkaç satırını değiştirmemiz gerekir. Yalnız bu noktada Linux türevlerine göre farklılıklar var.</li>
</ol>
Ubuntu için:

<em><strong>gksudo gedit /boot/grub/menu.lst</strong></em> kodu terminale yazılır ve entera basılır.

Kubuntu için:

<strong><em>kdesu kate /boot/grub/menu.lst </em></strong>kodu terminale yazılır ve entera basılır.

<strong><em> </em></strong><em>Xubuntu için:</em>

<strong><em>gksudo mousepad /boot/grub/menu.lst </em></strong>kodu terminale yazılır ve entera basılır.

Uygun sürüme göre yukarıdaki işlem yapılınca karşıya çıkan text editordeki metinde şu kısım bulunur:

# You can specify 'saved' instead of a number. In this case, the default entry
# is the entry saved with the command 'savedefault'.
# WARNING: If you are using dmraid do not use 'savedefault' or your
# array will desync and will not let you boot your system.
default	 0

Buradaki "default 0" kısmının değiştirilmesi gerekir. 0'ın anlamı bilgisayar açılırken karşıya çıkan ekranın 0. satırında yani en üst(ilk) satırında Ubuntu olduğu için onun açılacağıdır. Ancak ordaki 0 Windows XP yazan satırın numarasıyla değiştirilirse XP otomatik olarak açılır. Bu nedenle bu işlemi uygulayan kişi kendi bilgisayarının açılış ekranında XP'nin kaçıncı satıda olduğunu sayıp ona göre değiştirmelidir. Örneğin bende "default 8" olarak durmakta.

**Bu kısım isteğe bağlıdır. Yukarıdaki işlemlerden sonra bilgisayar açıldığında boot ekranı karşıya gelecektir. Kullanıcı 10 saniye tepki vermezse doğrudan XP açılacaktır. Ama bu 10 saniye fazla olabilir. Ben onu 3 saniye yaptım. Bunu yapmak için de:

## timeout sec
# Set a timeout, in SEC seconds, before automatically booting the default entry
# (normally the first entry defined).
timeout	 10

Bu kısım yine menu.lst'de bulunur. "default 0" satırından sonra başlayan bölümdür. Buradaki "timeout 10" satırındaki 10, 10 saniye gecikme olacağını temsil eder. Bunu kendinize göre bir saniye değeri vererek değiştiribilirsiniz.