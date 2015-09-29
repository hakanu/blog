---
layout: post
title: Ubuntu 9.10 kurulu bilgisayarda varsayılan olarak açılan işletim sistemini
  değiştirme
date: '2010-02-20 13:59:13'
---

Başlığa gel. Esasında "Default Boot işletim sistemini değiştirme" tadında bişi olacaktı. Türkçe kullanmak daha güzel. Her neyse geçen gün birisi yorum yapmıştı Ubuntu 9.10'da benim daha önce anlattığım yöntem çalışmıyor diye. Oluyodur sen yapamamışsın demeye getirdim özür diliyorum ondan. Grub güncellenmiş 1.97beta4 versiyonuna o yüzden 9.10'da yani Karmic Koala'da daha önce anlattığım yöntem işlemiyor. Biraz araştırıp aslını buldum. Her şey sizin için.

1) Grub'un önceden konuşlandığı nokta <code>/boot/grub/menu.lst </code>idi. Lakin şu anda öyle bir dosya yok. Eğer terminalden ulaşmaya çalışırsanız hata almanız normaldir. Ben aldım mesela. 9.10'da grub <code>/boot/grub/menu.cfg </code>konumundadır. Buraya dikkat <span style="color: #ff0000;">KESİNLİKLE BU DOSYAYI DEĞİŞTİRMEYİN</span>. Ha bi delilik yapıp değiştiririm ben demeyin dur anlatcam. Başka şeyi değiştircez

2) Bunun diğer dosyaları var bi de bizim eski menu.lst'ye benzeyen. Onu değiştirmemiz lazım o da şurda ikamet ediyor:

<code>/etc/default/grub</code>

3) Önce root olalım. Uygulamalar -&gt; Donatılar -&gt; Uçbirim yolunu izleyip terminali açalım ve şunu yazalım
<pre><span style="font-size: small;">sudo su</span></pre>
4) Değiştirmemiz gereken grub dosyası sistem dosyası olduğu için root olarak açıp değiştirmemiz gerekiyor. Bunun için de terminale
<pre><span style="font-size: small;">gksudo gedit /etc/default/grub
</span></pre>
<span style="font-size: small;">5) Şöyle bir dosya çıkacak karşımıza</span>
<div>
<pre># If you change this file, run 'update-grub' afterwards to update
# /boot/grub/grub.cfg.

<span style="color: #800080;">GRUB_DEFAULT=0</span>
#GRUB_HIDDEN_TIMEOUT=0
GRUB_HIDDEN_TIMEOUT_QUIET=true
<span style="color: #800080;">GRUB_TIMEOUT=10</span>
GRUB_DISTRIBUTOR=`lsb_release -i -s 2&gt; /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
GRUB_CMDLINE_LINUX=""

# Uncomment to disable graphical terminal (grub-pc only)
#GRUB_TERMINAL=console

# The resolution used on graphical terminal
# note that you can use only modes which your graphic card supports via VBE
# you can see them in real GRUB with the command `vbeinfo'
#GRUB_GFXMODE=640x480

# Uncomment if you don't want GRUB to pass "root=UUID=xxx" parameter to Linux
#GRUB_DISABLE_LINUX_UUID=true

# Uncomment to disable generation of recovery mode menu entrys
#GRUB_DISABLE_LINUX_RECOVERY="true"
</pre>
6) Bunun <span style="color: #993300;">GRUB_DEFAULT</span> satırının karşısına grub menüsünde hangi işletim sisteminin varsayılan olarak seçilmek istenirse onu yazıyoruz. Bunu sayarken 0'dan başlayarak sayın yalnız. Mesela şu anda Ubuntu 9.10 açılıyor ya GRUB'da bu 0. işletim sistemidir. Windows XP/Vista/7 büyük ihtimalle 3 ya 4'tedir. Güncelleme yaparsınız bu 6'ya kadar gidebilir. Onu siz bilgisayarı açarken sayın ve <span style="color: #993300;">GRUB_DEFAULT</span> değerini değiştirin.

7) İsterseniz GRUB ekranında bekleme süresini de değiştirebilirsiniz. Bunun için de <span style="color: #993300;">GRUB_TIMEOUT</span>=10 yazan satırdaki 10'dan daha küçük bir saniye değeri girebilirsiniz.

8 ) Dosyayı kaydedip çıkın. Root olduğunuz için kaydedecektir. Aksi halde izin vermez. İşimiz daha bitmedi.

9) Son olarak da terminalden şu kodu çalıştırıyoruz

update-grub

10) Şuna benzer bir ekran görünecek terminalde:
<pre>Generating grub.cfg ...
Found linux image: /boot/vmlinuz-2.6.31-14-generic
Found initrd image: /boot/initrd.img-2.6.31-14-generic
Found memtest86+ image: /boot/memtest86+.bin
Found Microsoft Windows XP Home Edition on /dev/sda1
done
</pre>
11) Bir dahaki başlatmanızda artık diğer işletim sisteminiz default olarak açılacaktır. Hayırlı olsun.

<span style="color: #ff6600;">Hakan UYSAL</span> (diğer siteler çalıyorlar nolur nolmaz)

</div>
<span style="font-size: small;">
</span>

<span style="font-size: small;"> </span>

<span style="font-size: large;">
</span>