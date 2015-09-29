---
layout: post
title: C'den Assembly Methodu Çağırma
date: '2010-11-01 21:06:51'
---

Bildiğiniz gibi hem C programlama dilinden Assembly methodlarını hem de tam tersi durumu yani Assembly'den C methodlarını çağırabiliriz(Artık bilmiyorsanız da öğrendiniz). Orta düzey bir programlamadan üst düzey programlamaya giriş yapmak isteyen ve bunu daha çok C ve Assembly ile yapmak isteyenlerin en çok aradığı şeylerden biridir bu özellik. Şimdi ikisini de anlatalım. İlk olarak kolay olandan Assembly'den C methodlarını çağırmayla başlayalım. Aslında bunda çok fazla bir sihir yok. Sadece asm uzantılı dosyamızın en üstüne çağırmak istediğimiz methodu yazıyoruz ve gerekli yerde call ile çağırıyoruz.

<a href="http://devdala.files.wordpress.com/2010/11/resim1.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/11/resim1.jpg" alt="" width="387" height="217" /></a>

Yukarıda işlerin nasıl olduğu ile ilgili küçük bir ekran görüntüsü koydum. Dikkat ettiğiniz gibi yukarıda anlatılanlara ek olarak çağırdığımız methodun parametreleri de olabilir. Böyle bir durumda ilk olarak en son parametreden başlayarak ilk parametreye kadar(n, n-1,..., 1 sırasıyla) her parametre stack'e atılır ve method çağırılır. İşlem bu kadar.

Şimdi gelelim daha ilginç işleme C'den Assembly methodunu çağırmaya. C içerisinde _asm bloğunun içerisine Assembly kodu yazılabiliyor. Ancak eğer bazı durumlarda asm uzantılı dosyamızdaki bir methodu çağırmak isteyebiliriz(Neden bilmiyorum). Böyle bir durumda ilk olarak yapacağımız C dosyamızın en üstünde methodun ... eklerken başına yine extern keyword'unu ekliyoruz. C dosyamızda yapacaklarımız şimdilik bu kadar.
<a href="http://devdala.files.wordpress.com/2010/11/resim-2.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/11/resim-2.jpg" alt="" width="387" height="157" /></a>
Ardından asm uzantılı dosyamıza C dosyamızdaki methodun ismiyle aynı olacak bir etiket tanımlıyoruz. Bu etiketin tam üstüne de  olacak şekilde bir satır ekliyoruz. Böylece etiketimiz global olacak. Sonra da etiketten sonra ne yapmak istiyorsak gerçekleştiriyoruz. Unutmadan C'den yolladığımız parametreler elbette stack'te olacak, hatırlatıyım dedim.
<a href="http://devdala.files.wordpress.com/2010/11/resim3.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/11/resim3.jpg" alt="" width="387" height="174" /></a>

Şimdi sıra geldi Assembly ve C dosyamızı derlemeye. Derleme işleminde ilk önce bir dosyanın .o dosyasını  sonrada diğer dosyanın .o dosyasını oluşturuyoruz. Son olarak da bu ikisinden çalıştırılabilir dosyamızı elde ediyoruz. Burada dikkat etmemiz .o dosyalarını oluştururken birinin ismini kendimiz verelim ki çakışma olmasın. Derleme işlemi için de aşağıdaki komutları kullanabiliriz.(örnek.c ve örnek.asm, sırasıyla C ve assembly dosyalar olmak üzere aşağıdaki komutları direk kullanabilirsiniz. Dosya isimleri farklıysa ona göre örnekdüzenleme yapın)
nasm -f elf örnek.asm -o örnek_asm.o
gcc -c örnek.c
gcc -o örnek örnek.o örnek.o

NOT: Anlatım Linux ve NASM için geçerlidir. MASM'da farklılık gösterebilir.

<em>-Serkan ÇAKMAK</em>