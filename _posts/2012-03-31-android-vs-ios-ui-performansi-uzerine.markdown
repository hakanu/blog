---
layout: post
title: Android vs iOS UI performansi uzerine
date: '2012-03-31 16:31:32'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2012/03/bscap0658.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/03/bscap0658.jpg" alt="" width="605" height="340" /></a></p>
Android cok kasiyo yeaa.

Dun gecemi buna ayirdim oturdum neler yazilmis cizilmis okudum azcik.

Bu arkadas Android testing takiminda stajyermis. Olaylar silsilesini baslatan, ilk hizi veren arkadas. Kendi cikarimlarini yazmis g+ postunda:

<a href="https://plus.google.com/u/0/100838276097451809262/posts/VDkV9XaJRGS">https://plus.google.com/u/0/100838276097451809262/posts/VDkV9XaJRGS</a>

Bu da elemanin profili:

<a href="http://www.linkedin.com/in/andrewmunn">http://www.linkedin.com/in/andrewmunn</a>

Cok parlak bi adam. Benim de bu satirlari okuyan ve hala ogrenci olanlara yegane tavsiyem stajlariniz icin kesinlikle yurtdisina basvurun.  Emin olun cok sey ogreneceksiniz. Benim pismanligimdir bu ayni zamanda. Olmaz demeyin kendi potansiyelinizi kucumsemeyin. Hem bi corporate gorun hem de yurtdisinda kisa surede yasamis olun. Neyse bunlari baska bir yazida ele aliyim ben.

Bob Lee nam-i diger crazybob ki kendisi dependency injection frameworku guice'in yaraticisiymis(Dun ogrendim). Android core library dev teaminde de team leadlik yapmis. Baya baya parlak bi eleman yani. Bu da onun cevabi:

<a href="http://blog.crazybob.org/2011/12/truth-about-android-ios-ui-performance.html">http://blog.crazybob.org/2011/12/truth-about-android-ios-ui-performance.html</a>

Bu da Dianne Hackborn tarafindan yazilmis ki kendisi Android Framework Engineer olarak gugilda calismakta gayet detayli, cok teknik terimle bogulmamis, her seyi cok guzel aciklayan bir post:

<a href="https://plus.google.com/u/0/105051985738280261832/posts/XAZ4CeVP6DC">https://plus.google.com/u/0/105051985738280261832/posts/XAZ4CeVP6DC</a>

Pek okumayi seven bi millet degiliz dogruya dogru ama maksimum 15 20 dakikanizi alacak yazilar. Uzun degiller. Sagdan soldan duyduklarinizla dezenformasyona ugrayacaginiza kendiniz okuyup ogrenin.

Disclaimerimi koyayim. Burda yazdiklarim superdogru seyler demiyorum kesinlikle. Sadece benim okuduklarim ve bildiklerim ya da bildigimi sandiklarim.

Benim okuduklarimdan anladiklarimi ve biraz da onceden bildiklerimi harmanlayip ozet gecmek gerekirse; bildigimiz birkac sey var. Android bytecode calistiriyor. java'yi az bucuk bilenler elbet duymuslardir bunu. Java'nin hem buyusu ve hem de lanetidir. Turkce'ye cevirince pek bi anlami olmadi gerci. En basit haliyle java'yi platformdan bagimsiz calistiran da budur, yavas calismasina sebep olan da. Bytecode JVM (Java Virtual Machine) tarafindan yorumlanir ve isletilir. Android'de de ozellesmis bir JVM var. Adi Dalvik. Gormus olabilirsiniz. Dalvik cache olaylari. iOS ne kullaniyor peki? Objective c tabanli gelistirme yapiliyor iOS'te. Cok fazla sey bilmiyorum ama native code kullanildigindan eminim. Native code temelde uzerinde bulundugu makinanin islemcisine(CPU) uygun olarak yazilmis kod demek. Yani goruldugu uzere bir platform dependency mevcut. x86'ya yazdiginiz C++ programinizi (exe) 64 bit bi bilgisayarda calistiramamaniz gibi. 64 bite uygun output verecek bir compiler ile tekrar derlemeniz gerekir kodu. Eger iyi bi cocuk olursaniz kod error vermeyebilir. Her neyse gunumuzde her taraf dil oldugu icin kisa bi ornek verecegim. C/C++ ile yazilmis programlar native code uzerinden isletilir. Bu yuzden platform bagimsizdir denemez. Java bu noktada siyrilir. Ama tabi ki takdir edersiniz ki eger bi program uzerinde calisacagi hedef CPU icin ozel olarak optimize edilirse elbette daha hizli ve stabil calisir. C++ neden benchmarklarda hep en hizlidir? Yetmez ama evet Intel Performance Primitives diye bir library cikardi. Intel cpularda guzel optimizasyon yaptiriyor programciya. Gibi gibi. iOS ve Windows phone 7 native code kullaniyor(mus). Wp7'i yeni ogrendim. Tamamen Silverlight tabanli olacak saniyordum ama yavas oldugunu gorunce cekirdegi native code a dondurmusler. Bu yuzden wp7li telefonlarin ui'lari oldukca akici. Bilmiyorum hic denediniz mi de. Ozellik wp7.5 mangoya bakilmasina. Youtube'da da videolari var.

Android de native code a donsun nolcak ki? Android'in ya da Google'in amaci hic bir zaman kullaniciyi kisitlamak olmadi. Bu benim tamamen objektif gozlemim. Reklam gecmis gibi olmasin alttan. 8 ay once de bunu dusunuyordum. Hep en iyi hizmeti, en iyi kullanici deneyimiyle, en kolay ve en hizli sekilde yapmayi amacladiklari butun urunlerinde goruluyor. Android'de de bunu amacliyorlardi tabi ki. iOS'e karsi durabilen yegane isletim sistemi olarak bir nevi de basariyorlar. Dianne cok guzel bir cumleyle baslamis yazisina Google'in ya da Android'in amaci guvenli ve ozgur bir ortam olusturabilmek. Bi otorite tarafindan kontrol edilen tek bir kaynaktan yazilim/uygulama dagitilan bir ortamdan ziyade. Cok guzel bir yaklasim bu. Apple'in yaptigi gibi her seyi kisitlamak, tek bir appstore olmasi, isolate edilmis bir ortamda uygulama gelistirip, tamamen belli bir islemci (donanim) icin optimize edilmis bir ortam yaratmak Google icin imkansiz mi? Tabi ki degil. Ama amaclari bu degil ki adamlarin. Android'in amaci sandboxlar olusturup uygulamalarin hepsini kendine ayrilan ortamda calistirip zararli bile olsa kullaniciya zarar vermesini engellemek. Bunun icin de bazi tradeofflara gitmiyorlar mi gidiyorlar.

Hani o kadar yazdin da UI akiciligiyla ne ilgisi var diyenler icin simdi bagliyorum. Soyle de ilginc bir nokta var. Ne kadar dogru bilmiyorum. Android ilk basta blackberry'ye rakip olarak dogmus. iOS yoktu tabi o zamanlar. Yani touch screen den ziyade trackball u klavyeli bir ortama optimize yapilmis. Sonradan Apple iPhone'u patlatinca apar topar touch screen UI'a gecilmis. Dolayisiyla Android'in UI frameworku biraz aceleye gelmis. Bilmiyorum ne derece dogru bunlar. Ama Google'in aceleye gelmis kodu bile guzeldir eminim ondan. UI Frameworkunun tekrar yazilmasi imkansiz mi peki Google niye bunu yapmiyor. Imkansiz degil ama bilindigi uzre su an android 4. versiyonunda ve legacy support olmasi lazim. 200 milyon android telefon varken ui frameworkunu bastan yazdik demek biraz abes olabilir bence. Onun yerine android takimi cok daha onemli ozelliklere odaklanmis durumdalarmis. Hardware acceleration gibi.

Stajyer arkadasin iddiasi, Android ui threadinin onceligini normal threadlerle ayni yaptigi icin o kadar akici degilmis. Mesela diyor; iphone'da safari'yi acip bi websitesi acin yuklemeye baslasin ve o yuklerken ekrana parmaginizi basili tutun, her sey duruyor diyor. Ama android'de hem sayfayi yukluyor hem de parmagi takip ediyor diyor. Yani iOS ui threadini top priority yapmisken Android bunu yapmiyormus. Dianne'in yazisini okuduysaniz cevap var orda. Diyor ki android thread priorityleri surda acik sekilde yazilmis:

<a href="http://developer.android.com/reference/android/os/Process.html#THREAD_PRIORITY_AUDIO">http://developer.android.com/reference/android/os/Process.html#THREAD_PRIORITY_AUDIO</a>

Ve devam ediyor. Android'de iki tane ana thread onceligi var diyor. Background ve ui. Background thread ki bu daha az oncelikli diyor. ve bir de main thread. Main thread'in onceligi default. Background threadinden daha oncelikli yani. UI renderi da main threadde yapiliyor.  Yani sorun thread onceliklendirmesi degil o kadar da. Bu arada background onceligindeki appler %10'dan fazla islemciyi kullanamiyorlarmis ki bu da arkada cok uygulama acik olsa yavaslar mi telefon veya sarjim gider mi sorularina guzel bi cevap.

Gozlemleyebileceginiz uzere dual core android telefonlar yeni yeni iphone 3gs'in akiciligina yaklasabiliyor. Android de aradaki farki bu islemci gucuyle kapatmaya calisiyor.

Daha fazlasi icin Dianne'in yazisini okumanizi tavsiye ediyorum.

Gelecegi gayet parlak rahat olabiliriz:-O 5. versiyonda herkeste buyuk umut var. Ha ben mi ben ICS'i cok seviyorum.

Telefon dedigin takilmicak arkadas.