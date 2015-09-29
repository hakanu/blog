---
layout: post
title: Google Chrome'a greasemonkey scriptleri eklemek
date: '2009-08-29 23:41:32'
---

<strong><em>Okumadan önce not:</em> Eğer ki Google Chrome 4+ kullanıyorsanız artık resmi olarak bu scriptlere destek var demektir. Yani userscripts.com'a girip istediğiniz scripti install dediğiniz zaman script direkt olarak Chrome uzantısı(extension - eklenti de diyebiliriz) olarak kurulur. Bu nedenle aşağıdaki işlemlere hiç gerek yoktur. Onlar eski Chrome'lar içindi. Ama ben uğraşırım diyenler yapabilirler tabi:D</strong>

<span style="background-color: #ffffff;">Firefox'un en kral eklentisi Greasemonkey'i Google Chrome'da kullanmak için yapılması gereken birkaç adım şöyle (XP için):</span>

"<em>C:\Documents and Settings\%kullanici adi%\Local Settings\Application Data\Google\Chrome\User Data\Default\User Scripts</em>" yerine greasemonkey scriptleri koyulur. (eğer bu konumda "User Scripts" klasörü yoksa oluşturmanız gerekir)

Herhangi bir chrome.exe'ye sağ tıkla hedefi şu şekilde değiştir: "<em>C:\Documents and Settings\%kullanici adi%\Local Settings\Application Data\Google\Chrome\Application\chrome.exe</em>" --enable-user-scripts

Yani sonuna
<pre><strong><span style="color: #000000;"> --enable-user-scripts</span></strong></pre>
eklenir.

Hem Firefox'ta hem Chrome'da çalışan birkaç script:

<em><strong>Adsweep:</strong></em> Sitelerde çıkan saçma sapan reklam bannerlarını engeller. İndirmek için:

<a href="http://www.adsweep.org/">http://www.adsweep.org/</a>

Yukarıdaki adresten betik indirildikten sonra Chrome'da yukarıda açılan "User Scripts" klasörünün içine kopyalanır. Artık sitelerdeki reklamlar engellenecektir. Betiğin çalıştığını teyit için <a href="http://www.adsweep.org/">http://www.adsweep.org/</a> adresine girip sağ üst köşede "Your AdSweep is currently active" yazısını görmek yeterlidir.

<span style="text-decoration: underline;">Firefox için şuradan kurulabilir:</span> <a href="http://userscripts.org/scripts/show/40933">http://userscripts.org/scripts/show/40933</a>**

<em><strong>Facebook Fixer:</strong></em> Facebook'ta her türlü küçük resmi açmadan önce üstüne gelerek beklendiğinde büyük şekliyle gösteren bir betiktir. Bütün albümü tek sayfada gösterebilir. Paylaşılan videolar için videonun penceresinin yanında "Download video" butonu oluşturur. Hatta videoyu izlediyseniz indirme yapmadan direk tarayıcı önbelleğinden çekip kaydettiğiniz yere yapıştırır.

<span style="text-decoration: underline;">Firefox için şuradan kurulabilir</span>: <a href="http://userscripts.org/scripts/show/8861">http://userscripts.org/scripts/show/8861</a>** adresinden "Install" Butonuna basılıp kullanılabilir.

<span style="text-decoration: underline;">Chrome için:</span> <a href="http://userscripts.org/scripts/show/8861">http://userscripts.org/scripts/show/8861</a> bu adresten jscript kodu kopyalanıp bir text dosyasına yapıştırılıp kaydedildikten sonra adına örneğin facebook_fixer.user.js yazıp "User Scripts" klasörüne atılarak kullanılabilir. Burada önemli olan ".user.js" kısmıdır.

**Tabi Firefox'ta bu betikleri kullanabilmek için greasemonkey eklentisinin yüklü olması gerekir. Yüklemek için:

<a href="https://addons.mozilla.org/en-US/firefox/addon/748">https://addons.mozilla.org/en-US/firefox/addon/748</a> adresinden "Add to Firefox" butonuna basılır.

Daha fazla betik için: http://userscripts.org