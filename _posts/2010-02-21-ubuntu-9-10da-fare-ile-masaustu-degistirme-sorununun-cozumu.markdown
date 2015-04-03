---
layout: post
title: Ubuntu 9.10'da fare ile masaüstü değiştirme sorununun çözümü
date: '2010-02-21 15:51:53'
---

9.10'a geçtik binbir dert oldu ne bu ya. 9.04 ile en mükemmel noktaya ulaştı sanırım Ubuntu sonra düşüşe geçti. Hayır niye her şeyi değiştiriyorsunuz ki mutlu mesut gidiyorduk. Neyse malum tek masaüstü yetmiyor. 2-4 kullanıyoruz. Küp kullananlar var. Masaüstünün boşluğuna gelip mouse wheel'ini scroll yapınca-vay yavrum cümleye gel- virtual desktopların change olması lazım ahaha. Yani fare tekerleğini çevirinice sanal masaüstleri arasında hızlıca geçiş yapabilmemiz lazım. Ama olmuyor deli ediyor. Araştırdım biraz sorunu buldum. Compiz'de bu özellik pasif olarak geliyor imiş. Hemen adımları uyguluyoruz:

1) Compiz yönetim paneliniz yoksa ki yeni kurulmuş bir Ubuntu'da bu yoktur. Hemen Synaptic Paket Yöneticisi'ni açıyoruz ve arama yerine "compizconfig" yazıp aratıyoruz. En üstte çıkar zaten. Ona basıp kuruyoruz.

2) Compizconfig kurulumu bitince Sistem -&gt; Tercihler -&gt; CompizConfig Ayar Yöneticisi diye bir öge oluşacak. Ona basıyoruz. Tadaa işte karşınızda Compiz'e ayar çekmek için envai çeşit ekran. Bunu zaten ortalama bi Ubuntu kullanıcısı bilir. Olur da bilmeyenler varsa diye.

3) Burdan "Masaüstü değiştirici"yi buluyoruz. Desktop Changer tarzı bişi olması lazım. Onun yanındaki tikin işaretli olması gerekiyor. Değilse işaretleyelim

4) "Masaüstü Değiştirici"ye basıp "Desktop-based Viewport Switching" sekmesine geliyoruz.

5) "Sonrakine taşı" ve "öncekine taşı" diye iki tane özellik var bunların karşısında pasif yazıyor. Pasife basıyoruz. "Etkin"i işaretliyoruz. Tuş atama gelecek. Klavyeden değil de altta mouse ile atama var. Ona basıyoruz. Orada farenin tuşlarına göre "Button1", "Button2" falan var. Sizin tekerlek kaç numaraysa ona göre yapın. Lakin tekeri ileri itmek(scroll) ayrı tuş geri çekmek ayrı tuş. Bi iki deneme yamulmayla sonuca ulaşabilirsiniz. Benimki şöyle mesela

<a href="http://www.hakanu.net/wp-content/uploads/2010/02/adhaha.png"><img class="aligncenter size-full wp-image-948" title="adhaha" src="http://www.hakanu.net/wp-content/uploads/2010/02/adhaha.png" alt="" width="749" height="350" /></a>