---
layout: post
title: İnternet üzerinden izlenen videoları bilgisayara programsız kaydetmek
date: '2009-09-06 12:03:14'
---

<p style="font-family:Calibri;font-size:11pt;margin:0;">İnternet üzerinden video izleme artık kullanıcıların vazgeçilmezi olmuşken buna paralel olarak online videoları bilgisayara indirmek için değişik araçlara da ücretsiz bir şekilde ulaşılabilmekte. Artık her indirme yöneticisinin içerisinde bütünleşik bir video indirici mevcut nerdeyse. Ayrıca birçok firefox eklentisi de bu amaca hizmet ediyor. Yalnız benim anlatacağım yöntemde herhangi bir program kullanmak yok. Sadece dosya yöneticisinde birkaç klasör gezinmek gerekiyor. Çünkü izlediğimiz her video aslında önce bilgisayara indiriliyor. Bu indirildiği konumdan videoyu alıp kopyalarsak tekrar indirmeye gerek kalmaz.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:13pt;margin:0;">Windows XP altında bazı tarayıcılar için videoların kaydolduğu konumlar:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><span style="color:red;">Mozilla Firefox için:</span></p>
<p style="font-style:italic;font-family:Calibri;font-size:11pt;margin:0;">C:\Documents and Settings\%Kullanıcı Adı%\Local Settings\Application Data\Mozilla\Firefox\Profiles\dufnteaa.default\Cache</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Buradaki <span style="font-weight:bold;font-style:italic;">dufnteaa.default </span>adlı klasör kişiden kişiye fark edebilir. O konumda zaten bir tek buna benzer bir isimli klasör bulunur.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Daha kolay yöntem ise Mozilla Firefox penceresinde<span style="font-style:italic;"> about:cache</span> yazılıp entera basmaktır. Bunun sonucunda bende "Cache directory" satırı şu şekilde çıkmaktadır ki bizi ilgilendiren de budur:</p>
<p style="font-weight:bold;font-family:Calibri;font-size:11pt;margin:0;">Cache Directory:</p>
<p style="font-style:italic;font-family:Calibri;font-size:11pt;margin:0;">C:\Documents and Settings\Administrator\Local Settings\Application Data\Mozilla\Firefox\Profiles\dufnteaa.default\Cache</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Bu yöntem Windows Vista için de geçerlidir.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Internet Explorer için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Başlat - Denetim Masası - İnternet Seçenekleri açılır. Buradan "Genel" sekmesinden "Gözatma Geçmişi" kısmı bulunur. "Ayarlar" butonuna basılır. Çıkan yeni pencerede "Dosyaları görüntüle" butonuna basıldığında internet explorer cache klasörüne erişilmiş olur. Buradaki dosyalar boyutlarına göre büyükten küçüğe sıralanırsa en büyük boyutlu olanlar videolar olacaktır. Zaten Internet Explorer'da izlenen videolar doğrudan video olarak görünmektedir. Kolaylıkla izlenen video o dosyaların içinden seçilebilir. Firefox'ta olduğu gibi sonuna .mpg veya .flv tarzı uzantı yazmaya gerek yoktur.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Google Chrome için:</p>
<p style="font-style:italic;font-family:Calibri;font-size:11pt;margin:0;">C:\Documents and Settings\%Kullanıcı adı%\Local Settings\Application Data\Google\Chrome\User Data\Default\Cache</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Opera için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Opera için de Firefox'a benzer bir yöntem vardır. Opera'nın adres çubuğuna <span style="font-style:italic;">opera:cache</span> yazılıp cache'e ulaşılabilir.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:13pt;margin:0;">Windows Vista altında bazı tarayıcılar için videoların kaydolduğu konumlar:</p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Mozilla Firefox için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Firefox penceresindeki adres çubuğuna<span style="font-style:italic;"> about:cache</span> yazıp "cache directory" satırındaki adrese girmek daha garanti olsa da genel bir adres örneği şu şekildedir:</p>
<p style="font-style:italic;font-family:Calibri;font-size:11pt;margin:0;">C:\Users\%kullanıcı adınız%%\AppData\Local\Mozilla\Firefox\Profiles\dufnteaa.default\Cache</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Google Chrome için:</p>
<p style="font-style:italic;font-family:Calibri;font-size:11pt;margin:0;">C:\Users\%Kullanıcı adınız%\AppData\Local\Google\Chrome\User Data\Default</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Opera için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Opera için de Firefox'a benzer bir yöntem vardır. Opera'nın adres çubuğuna <span style="font-style:italic;">opera:cache</span> yazılıp cache'e ulaşılabilir.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-weight:bold;font-family:Calibri;font-size:13pt;margin:0;">Ubuntu ve türevleri olan Linux sürümlerinde videoların kaydolduğu konumlar:</p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Mozilla Firefox için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Yine yukarıdaki gibi Firefox penceresinin adres çubuğunda <span style="font-style:italic;">about:cache</span> yazılarak "Cache directory" konumu bulunur. Buradan bu konuma girilip ilgilendiğimiz klasöre ulaşılır.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;color:red;margin:0;">Opera için:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Opera için de Firefox'a benzer bir yöntem vardır. Opera'nın adres çubuğuna <span style="font-style:italic;">opera:cache</span> yazılıp cache'e ulaşılabilir.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Bu klasöre ulaştıktan sonra yapmamız gereken ordaki garip isimli dosyaları boyutlarına göre dizmek olmalıdır. Dizdikten sonra en büyük boyutlu dosyalarla ilgileneceğiz. Bu dosyalar uzantısızdır o yüzden ne olduğunu bilemeyiz. Ancak Firefox cache klasörünü ele alırsak, bir video izlendiğinde bu klasörde 4-5 mb lik bir dosya oluşur. Eğer böyle bir dosya oluşursa ve adı da _CACHE ile başlamıyorsa bu bizim ilgilendiğimiz videodur. Bunu oradan videoyu kaydetmek istediğimiz yere kopyalarsak elimizde 4-5 mb lik uzantısız bir dosya olmuş olur. Bu dosyayı kullanmak için sağ tıklayıp adını değiştiririz ve adının sonuna ".mpg"(tırnaklar olmadan) yazılırsa uzantısız dosya video dosyası olur ve artık rahatlıkla izlenebilir.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">Eğer oluşan dosyayı izleyemiyorsanız kodek dosyalarınız eksiktir. Alttaki linkteki kodek pakedini bir kereye mahsus olmak üzere kurarsanız her türlü video formatını rahatlıkla izleyebilirsiniz:</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"><a href="http://download.softpedia.com/dl/5588790866e540105cfa2bf00a3e1678/4aa3a37e/100015909/software/multimedia/video/divx/K-LiteCodecPack510Mega.exe">http://download.softpedia.com/dl/5588790866e540105cfa2bf00a3e1678/4aa3a37e/100015909/software/multimedia/video/divx/K-LiteCodecPack510Mega.exe</a></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;">NOT: HD videoların boyutları çok büyük olduğu için karşıdan indirilme bittiği anda cache klasöründen silinirler. Bu yüzden videonun yüklenmesinin bitmesine az bir süre kala uzantısız dosya cache klasöründen başka bir yere kopyalanırsa silinmeden kurtarılabilir. Aksi halde temp klasöründe bekletilir. Buradan da almak imkansızdır. Sürekli dosya kullanımda uyarısı alınır.</p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>
<p style="font-family:Calibri;font-size:11pt;margin:0;"></p>