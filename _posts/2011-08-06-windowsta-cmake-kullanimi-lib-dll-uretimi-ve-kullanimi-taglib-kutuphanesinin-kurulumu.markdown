---
layout: post
title: Windows'ta Cmake kullanımı, lib-dll üretimi ve kullanımı, taglib kütüphanesinin
  kurulumu
date: '2011-08-06 11:05:45'
---

Başlığa gel. Böyle posta böyle başlık. Mahsun kırmızıgül filmi tadında oldu. Büssürü konuya el atıp hiç birini çözemeden okuyucuyu ortada bırakicim.
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2011/08/conidep.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/conidep.jpg" alt="" width="626" height="346" /></a></p>
Cmake cross platform bir build aracı. Onun sayesinde istediğiniz compiler a göre çıktı ürettirebiliyorsunuz. Nevet nerdeyse bütün derleyicileri destekliyor. Gayet de güncel VS 2010 desteği de var uzunca bir süredir.

Cmake kullanımı için örnek bir kütüphane kullanımı da anlatıcam. Bu kütüphanemiz taglib adlı mp3 taglerini okumaya yarayan bir api. Bu aralar mp3 arşivimi düzenlerkene niye bunları elimle yapıyorum derken buldum kendimi. Taglib amarok, jaangle gibi programların arkasındaki tag engine imiş. Alanında en hızlıymış. Neyse. Ayrıntısı sora.

Öncelikle herkesin bildiği bikaç gereksiz bilgi: lib dosyaları kütüphane(library) dosyaları olup exe oluşturulurken derleme anında statik olarak bağlanırlar. dll dosyaları ise adından da anlaşıldığı üzre dynamic link library olup runtime esnasında doğrudan dinamik olarak kullanılırlar. Ha noldu bu durumda exe'ye tıklandığında dan diye uyarı çıkıp şu dll missing diyosa bu dinamik bir bağlanmadır. lib eksikse zaten compile time'da error gelir.
<ol type="1">
	<li value="1">Taglib indirilir</li>
</ol>
<a href="http://developer.kde.org/~wheeler/taglib.html">http://developer.kde.org/~wheeler/taglib.html</a>
<ol type="1">
	<li value="2">Taglib'in çeşitli dependencyleri yok değil. Zlib'in bilgisayarınızda kurulu olması lazım. Onun için de:</li>
</ol>
<a href="http://sourceforge.net/projects/gnuwin32/files/zlib/1.2.3/zlib-1.2.3.exe/download">http://sourceforge.net/projects/gnuwin32/files/zlib/1.2.3/zlib-1.2.3.exe/download</a>
<ol type="1">
	<li value="3">Cmake indirilip kurulur</li>
</ol>
<a href="http://www.cmake.org/cmake/resources/software.html">http://www.cmake.org/cmake/resources/software.html</a>
<ol type="1">
	<li value="4">Cmake açılır. Taglib içindeki CMakeLists.txt cmake üzerine bırakılır.</li>
</ol>
<a href="http://devdala.files.wordpress.com/2011/08/1.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/1.png" alt="" width="700" height="156" /></a>

Cmake'ten configure butonuna basılır

<a href="http://devdala.files.wordpress.com/2011/08/2.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/2.png" alt="" width="494" height="184" /></a>
<ol type="1">
	<li value="5">Çıkan pencereden kendinize uygun compiler seçilir. Bende Visual Studio 2010 kuruluydu o anda. Ordan devam edicim. Vs 2008 Sp1 kuruluysa Visual Studio 9'u seçmelisiniz. Neyse Finiş diyoruz. Bu esnada Visual sütüdyonun kapalı olduğundan emin olun. Cmake kızarır generate etmez yoksa.</li>
</ol>
<ol type="1">
	<li value="6">Cmake'in orta kısımdaki listesinde birtakım parametrelerin olduğunu görürsünüz. Burası bizim generation işleminin parametreleri aslında. Cmake'in en güzel yanı burda. Parametrelere göre istediğinz ortama göre kod üretiyor. Ben şöyle ayarladım:</li>
</ol>
<a href="http://devdala.files.wordpress.com/2011/08/3.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/3.png" alt="" width="700" height="348" /></a>
<ol type="1">
	<li value="7">ENABLE_STATIC yapamadım ben. Dll çıkarmıyor onu işaretleyince. Ama kodlar da derlenmiyor. 3 saatime mâloldu sağolsun. CPPunit ne ola ki diyenleri duyar gibiyim. O da bilmem bilir misinz birim test yapmak için bir modül. Junit'e benziyor bizim. Olmasa da olur. Hata verirse sallayın.</li>
</ol>
<ol type="1">
	<li value="8">Ayarlarımızı yaptıktan sora "Generate" diyoruz. Ve tadaa VS solution dosyaları oluşacak.</li>
</ol>
<ol type="1">
	<li value="9">Cmake'e bayılmamak elde değil. "taglib.sln"i açıyoruz. Build-&gt; Build Solution diyoruz.</li>
	<li>Taglib klasörümüzün altındaki Debug klasörüne bir adet .lib ve bir adet .dll uzantılı dosya oluşturulmuş olması lazım. Oluşmadıysa kötü.</li>
</ol>
..\taglib-1.7\taglib-1.7\taglib\Debug
<ol type="1">
	<li value="11">Şimdi bunları kullanarak bi proje oluşturacağız. Burada Visual Studio'da lib ve dll dosyaları nasıl kullanılır görmüş olunur.</li>
<ol type="a">
	<li value="1">Yeni vs c++ projesi oluşturulur.</li>
</ol>
<ol type="a">
	<li value="2">Cpp açılıp şu örnek kodu yazabilirsiniz(taglib examplelarından çarptım kodu. Azcık modifiye ettim. Exe'nin yanında f.mp3 olmalı çalışması için. Tabi ki f.mp3'ün tagleri falan düzgün olursa çalışma daa iyi gözlenir):</li>
</ol>
</ol>
<code>
<pre lang="cpp" line="1">
#include "fileref.h"
#include "tag.h"
#include "iostream"
using namespace std;
int main(int argc, char *argv[])

{

char str[50] = "f.mp3";

TagLib::FileRef f(str);

if(!f.isNull() && f.tag()) {

TagLib::Tag *tag = f.tag();

cout << "-- TAG --" << endl;

cout << "title   - \"" << tag->title()   << "\"" << endl;

cout << "artist  - \"" << tag->artist()  << "\"" << endl;

cout << "album   - \"" << tag->album()   << "\"" << endl;

cout << "year    - \"" << tag->year()    << "\"" << endl;

cout << "comment - \"" << tag->comment() << "\"" << endl;

cout << "track   - \"" << tag->track()   << "\"" << endl;

cout << "genre   - \"" << tag->genre()   << "\"" << endl;

}

if(!f.isNull() && f.audioProperties()) {

TagLib::AudioProperties *properties = f.audioProperties();

int seconds = properties->length() % 60;

int minutes = (properties->length() - seconds) / 60;

cout << "-- AUDIO --" << endl;

cout << "bitrate     - " << properties->bitrate() << endl;

cout << "sample rate - " << properties->sampleRate() << endl;

cout << "channels    - " << properties->channels() << endl;

}

getchar();

return 0;

}
</pre>
</code>
<ol type="a">
	<li value="3">Şimdi projenin bağımlılıklarını ayarlamaya sıra geldi. Projeye sağ tık -&gt; Properties -&gt; C/C++ -&gt; General:</li>
</ol>
<div><a href="http://devdala.files.wordpress.com/2011/08/4.png"><img class="alignnone" src="http://devdala.files.wordpress.com/2011/08/4.png" alt="" width="754" height="182" /></a></div>
<ol type="a">
	<li value="5">Additional Include Directories'e headerların klasörlerini eklemeli</li>
</ol>
<ol type="a">
	<li value="6">Projeye sağ tık -&gt; Properties -&gt; Linker -&gt; Input:</li>
</ol>
<a href="http://devdala.files.wordpress.com/2011/08/5.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/5.png" alt="" width="748" height="340" /></a>

Eklenecekler şunlar:

C:\fw\taglib-1.7\taglib-1.7\taglib\Debug\tagd.lib

d:\Program Files\GnuWin32\lib\zlib.lib

<a href="http://devdala.files.wordpress.com/2011/08/6.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/6.png" alt="" width="355" height="506" /></a>
<ol type="a">
	<li value="7">Kodu build edince çalışması lazım. Ve hatta çıktısı da şöyle:</li>
</ol>
<div><a href="http://devdala.files.wordpress.com/2011/08/7.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/7.png" alt="" width="266" height="184" /></a></div>
Not: Exe çalışmayabilir ilk etapta. "tagd.dll" dosyasını bulamadım hatası verebilir. Tagd.lib'in olduğu yerde üretilen tagd.dll dosyasını kopyalayıp exe'nin yanına koyarsanız hata giderilir. Diğer yöntem ortam değişkenlerine tagd.lib ve tagd.dll'in olduğu klasörü eklemektir ki ben böyle bi kütüphane için pek gerekli görmüyorum o hareketi. Hani bi Qt kütüphanesi olur eklenir de taglib'e gerek yok.