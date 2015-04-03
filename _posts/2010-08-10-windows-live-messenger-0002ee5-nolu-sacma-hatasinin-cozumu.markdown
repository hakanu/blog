---
layout: post
title: Windows Live Messenger 0002ee5 nolu saçma hatasının çözümü
date: '2010-08-10 08:46:15'
---

Güneşli bir yaz gününde windows live messenger adlı garip programa tıkladığımda dank diye ekrana "hata raporu gönder/gönderme" şeysini çıkardı. Bi daa denedim yine çıktı. Reset attım yine çıktı. Şöyle bişi hata:

<a href="http://devdala.files.wordpress.com/2010/08/hata.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/hata.jpg" alt="" width="495" height="240" /></a>

<img class="aligncenter" src="http://devdala.files.wordpress.com/2010/08/hataayrinti.jpg" alt="" width="505" height="335" />

Sistemim Windows XP SP3 32 bit. Şimdi sorunun nasıl çözüleceğine bakalım:

- başlat-&gt;çalıştır'ı açıyoruz. "regedit" yazıyoruz "Tamam" diyoruz.

- Aşağıdaki kayıt girdisini açıyoruz.
<pre>HKEY_CURRENT_USER\Software\Microsoft\MSNMessenger\PerPassportSettings\</pre>
- Burda o zamana kadar kaç tane Live Messenger hesabıyla oturum açtıysanız hepsinin bilgisi tutuluyor. En son yani hatadan önce  hangi hesapla oturum açtıysanız onu buluyorsunuz. Sıradan bakın her sayıya. Tıklayınca sağ panelde bütün kayıt girdileri gözükür. "UTL" girdisine bakmak gerekiyor. Orda "name@hotmail.com" tarzı hangi mail adresiniz varsa onu gösteriyor. Ordan son açtığınız  oturumu bulun. (Nolur nolmaz silmeden önce o hesabın yedeğini alsanız iyi olur. Onun için de hesabın klasörünü işaretleyip Dosya -&gt; Ver diyip kaydetmek yeterli.) Onun UTL değerini silin. Garanti olsun derseniz bütün hesapların UTL değerlerini silebilirsiniz. Yedeğini alın tabi nolur nolmaz.

- Bilgisayarı yeniden başlatın. Artık kullanabilirsiniz wlm'yi rahatça. Bi aksilik olursa aldığınız yedek reg dosyalarını çalıştırın düzelir.