---
layout: post
title: Visual Studio'nun header ve library dosyalarını arama sırası
date: '2010-12-09 20:33:07'
---

<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/12/devdala-com-12.jpg"><img class="aligncenter" title="caps verdim pampa" src="http://devdala.files.wordpress.com/2010/12/devdala-com-12.jpg" alt="" width="504" height="284" /></a></p>
Canım sıkıldı bişiler yaziyim. Visual Studio'da göreli geniş bir proje yapıyorsanız ve başka başka kütüphanelerden faydalanıyorsanız bunları bir şekilde projeye include etmeniz gerekiyor. Bunları yapmanın birkaç yolu var.

Öncelikle şundan bahsedeyim newbieler için bir projede external bir fonksiyonu kullanmak için varsa o fonksiyonu içeren header dosyasını(.h uzantılı) include etmek gerekiyor. Misal #include&lt;stdio.h&gt; böyle bişidir. Bu durumda iş biraz daha kolaydır. Hızlı olur. Diğer durumda fonksiyon library file içinde olabilir ki bunlar da .lib ile biten paketlenmiş kütüphanelerdir. Bunları projeye dahil etmek için şöyle bir yol izlenebilir (Visual Studio 2008 ve SP1 için):

- Projeye sağ tıklanıp "Properties" e gelinir.

- Linker -&gt; Input kısmına gelinir. Ordan "Additional Dependencies"e gelinir ve karşısına aralara ';' (noktalı virgül-tırnaklar olmadan-)  koyarak istenen lib dosyalarının isimleri yazılır. Path değil dikkatinizi çekerim ismleri sadece.

Mesela şöyle bir görüntü oluşabilir:
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/12/librarydependecncy.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/12/librarydependecncy.jpg" alt="" width="449" height="313" /></a></p>
<p style="text-align: left;">Projeyi build ettiğinizde muhtemelen bıdıbıdı.lib dosyasını bulamadım abi der. Şöyle bir hata olur genelde yamulmuyorsam:</p>

<blockquote>
<pre>Unresolved external symbol</pre>
</blockquote>
<p style="text-align: left;">Neden çünkü bizim kullanmak istediğimiz lib dosyasının pathini alete vermedik. Olay da burada başlıyor işte.</p>
<p style="text-align: left;">Header ve lib dosyalarının pathlerini vermenin bir şekli şöyle:</p>
<p style="text-align: left;"><strong>1)</strong> <span style="color: #ff0000;">Header:</span>Projeye sağ tık Properties, C/C++ -&gt; General -&gt; Additional Include Directories. Buraya kod içinde #include&lt;bilmemne.h&gt; diye include ettiğimiz header dosyasının içerildiği pathi giriyoruz. Böylece external bir kütüphaneyi dilediğimiz gibi kullanabiliyoruz.</p>
<p style="text-align: left;"><span style="color: #ff0000;">Library file:</span> Bunun için de Projeye sağ tık Properties, Linker -&gt; General -&gt; Additional Library Directories'in karşısına yukarıdaki gibi kullanmak istediğimiz lib uzantılı dosyanın içerildiği pathi yazıyoruz. OK diyip çıkıyoruz. Rebuild solution tada hata kaybolacak. Başka bişi yoksa çalışacak muhtemelen.</p>
<p style="text-align: left;">Bu ilk çözüm takdir edersiniz ki projeye özel bir çözüm. Daha genel geçer bir çözüm aşağıda:</p>
<p style="text-align: left;"><strong>2)</strong> External header ve lib dosyalarını sık sık değişik projelerde kullanılacaksa bu yöntem daha uygun sanki. Visual Studio ana penceresinde Tools -&gt; Options -&gt; Projects and solutions -&gt; VC++ Directories'e gelinir. Sağ kısımın sağ üst köşesinde Show directories for yazar onun altındaki dropdown listten "Include files" veya "Library files"a gelerek istenen header veya lib dosyalarının içerildiği pathler yazılır. Böylece hiç projenin ayarlarını değiştirmeden buradan dahil edilebilir.</p>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/12/vc_directories.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/12/vc_directories.jpg" alt="" width="448" height="258" /></a></p>
<p style="text-align: left;"><strong>3)</strong> Bu biraz amelece olacak ama küçük ve az dosyalı bi kütüphaneyle çalışılıyorsa yapılabilir: headerları falan doğrudan projenin source klasörü içine atmak</p>

<h2 style="text-align: center;">Dosyaları arama sırası</h2>
<p style="text-align: left;"><strong>1.</strong> Build aşamasında ilk olarak ilgili source klasörüne bakılır</p>
<p style="text-align: left;"><strong>2. </strong>Proje Properties'indeki Additional Include Directories'de bakılır</p>
<p style="text-align: left;"><strong>3. </strong>Tools-&gt; Options'tan ayarlanan VC++ Directories'e bakılır</p>

<h2 style="text-align: center;">Pros&amp;Cons</h2>
<p style="text-align: left;">Bi kere 1. yöntemle hazırlanmış projeleri paylaşması paylaşılan insan için daha kolaydır. Çünkü bi de projenin ayarlarını yapmakla uğraşmaz doğrudan build edebilir tabi aynı pathlerde aynı kütüphaneler varsa.(ortam değişkenleri de aslında bunun için var bence). Taşınabilirlik artar. 2. yöntemde taşınabilirlik yok adam projeyi alınca bi de ayarlarını yapar include edilen liblerin yollarını bulup belirtir. Ama 2. yöntemde de sürekli yeni proje açtıkça aynı ayarlar yapılmayıp rahat edilir. 3. yöntemde de projenin boyutu falan büyüyor.</p>
<p style="text-align: left;">Benim yorumlamam bu kadar.</p>
<p style="text-align: left;"><em>- Hakan Uysal </em></p>
<p style="text-align: left;"></p>