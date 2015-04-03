---
layout: post
title: Mp3 dosyalarının taglerini (meta bilgilerini) okumak, değiştirmek
date: '2011-08-06 21:33:11'
---

mp3leri telefona veya bir programa atınca Track 7 yazmasından nefret edenlere gelsin bu yazı.
<div class="mceTemp mceIEcenter"><dl id="" class="wp-caption aligncenter" style="width: 624px;"><dt class="wp-caption-dt"><a href="http://devdala.files.wordpress.com/2011/08/bscap03091.jpg"><img class="   " src="http://devdala.files.wordpress.com/2011/08/bscap03091.jpg" alt="" width="614" height="346" /></a></dt><dd class="wp-caption-dd"></dd></dl></div>
Başlamadan önce biraz önbilgi: Mp3 dosyalarının sonunda 128 bitlik şarkı bilgileri için ayrılmış id3 diye bir veri yapısı vardır. id3v1, id3v2, id3v3 gibi versiyonları var. direk c'de fopen yapıp okuyabiliyoruz.  C'nin gözünü seviyim. v1 daha basitken, v2 ve v3te tagler başa alınmıştır ve daha çeşitlendirilmiştir (composer falan filan).

Taglib id3lib gibi kütüphaneler mevcut. Google'da 10 saniyelik bi aramayla çıkıyor bunlar. Gelgelelim nasıl kullanacağımıza.

1. Öncelikle taglibi kuralım. Kaynak koduyla geliyor. Derlemesi bize kalıyor. Ayrıntılı anlatım isteyenler şu tarafa gitti:

<a title="Taglib kurulumu" href="http://www.hakanu.net/?p=1785" target="_blank">Taglib kurulumu</a>

2. lib ve header dosyalarını yukardaki linke göre ayarlayıp projeyi düzgün açtığınızı varsayıyorum. Aşağıdaki kodu yeni bi cpp dosyasına yazıyoruz.

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
	<li value="7">Kodun çıktısı:</li>
</ol>
<div><a href="http://devdala.files.wordpress.com/2011/08/7.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/7.png" alt="" width="266" height="184" /></a></div>
<h1>Tagleri Değiştirmek/Kaydetmek</h1>
<div>İster yeni bir proje açabilirsiniz isterseniz aynı projeye yazabilirsiniz. Ben yeni bir projeymişçesine yazıyorum.</div>
<div>Kodumuz şu şekilde:(examplelardaki tagwriter.cpp yi modladım - size D:\Temp\f.mp3) yerine başka bişi koyarsınız.)</div>
<div>
<code>
<pre lang="cpp" line="1">
#include <iostream>
#include <string.h>

#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdlib.h>

#include <tlist.h>
#include <fileref.h>
#include <tfile.h>
#include <tag.h>

using namespace std;

bool isArgument(const char *s)
{
	return strlen(s) == 2 && s[0] == '-';
}

bool isFile(const char *s)
{
	struct stat st;
#ifdef _WIN32
	return ::stat(s, &st) == 0 && (st.st_mode & (S_IFREG));
#else
	return ::stat(s, &st) == 0 && (st.st_mode & (S_IFREG | S_IFLNK));
#endif
}

void usage()
{
	cout << endl;
	cout << "Usage: tagwriter <fields> <files>" << endl;
	cout << endl;
	cout << "Where the valid fields are:" << endl;
	cout << "  -t <title>"   << endl;
	cout << "  -a <artist>"  << endl;
	cout << "  -A <album>"   << endl;
	cout << "  -c <comment>" << endl;
	cout << "  -g <genre>"   << endl;
	cout << "  -y <year>"    << endl;
	cout << "  -T <track>"   << endl;
	cout << endl;

	cout << "cikilacak" << endl;
	getchar();

	exit(1);
}

int main()
{
	TagLib::List<TagLib::FileRef> fileList;

	char* str = "D:\\Temp\\f.mp3";

	if( isFile( "D:\\Temp\\f.mp3" ))
	{
		cout << "girdim" << endl;

		TagLib::FileRef f( str );

		if(!f.isNull() && f.tag())
		{
			cout << "koydum" << endl;

			fileList.append(f);
		}
	}

	if(fileList.isEmpty())
	{
		usage();
	}

	cout << "girdim" << endl;
	char field = 't';
	TagLib::String value = "Deli Coban";

	TagLib::List<TagLib::FileRef>::Iterator it;

	for(it = fileList.begin(); it != fileList.end(); ++it)
	{
		TagLib::Tag *t = (*it).tag();

		switch (field) {
		case 't':
			t->setTitle(value);
			break;
		case 'a':
			t->setArtist(value);
			break;
		case 'A':
			t->setAlbum(value);
			break;
		case 'c':
			t->setComment(value);
			break;
		case 'g':
			t->setGenre(value);
			break;
		case 'y':
			t->setYear(value.toInt());
			break;
		case 'T':
			t->setTrack(value.toInt());
			break;
		default:
			usage();
			break;
		}
	}

	for(it = fileList.begin(); it != fileList.end(); ++it)
	{
		TagLib::File* f = (*it).file();
		cout << "sarki : " << f->name() << endl;
		f->save();
	}

	/////////////Özellikleri yaz
	TagLib::FileRef f(str);
	TagLib::Tag *tag = f.tag();
	if(!f.isNull() && f.tag())
	{
		TagLib::Tag *tag = f.tag();

		cout << "-- TAG --" << endl;
		cout << "title   - \"" << tag->title()   << "\"" << endl;
		cout << "artist  - \"" << tag->artist()  << "\"" << endl;
		cout << "album   - \"" << tag->album()   << "\"" << endl;
		cout << "year    - \"" << tag->year()    << "\"" << endl;
		cout << "comment - \"" << tag->comment() << "\"" << endl;
		cout << "track   - \"" << tag->track()   << "\"" << endl;
		cout << "genre   - \"" << tag->genre()   << "\"" << endl;
	}
	//////////////

	getchar();

	return 0;
}
</pre>
</code>

</div>
<div>Görüldüğü üzre Feist'in canım şarkısının title'ini "Deli Coban" yaptık. Pişman mıyım hayır.</div>
<div><a href="http://devdala.files.wordpress.com/2011/08/feist.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/08/feist.png" alt="" width="261" height="100" /></a></div>
<div>Kutsal bilgi kaynağı'nda <a href="http://www.eksisozluk.com/show.asp?t=elcezire+exclusive">elcezire exclusive</a> nikli üstat id3v1 lerin C ile nasıl okunacağını gayet sade şekilde kodlamış. Emeğine saygı diyerek kodu bir de buraya koyuyorum:</div>
<div>
<code>
<pre lang="c" line="1">
#include <stdio.h>
struct tid3tag
{
	unsigned char id[3];
	unsigned char title[30];
	unsigned char artist[30];
	unsigned char album[30];
	unsigned char year[4];
	unsigned char comment[30];
	unsigned char genre;
};

int main()
{
	FILE *dosya;
	tid3tag ntag = {0};

	dosya = fopen("D:\\müzikler\\500 Days of Summer\\Feist - Mushaboom.mp3", "rb");
	if (dosya == NULL) { printf( "dosya acilamadi..."); return 0;}

	fseek ( dosya, -128, SEEK_END);
	fread ( &ntag, 1, sizeof(tid3tag), dosya);

	printf( "\n\n sarki: %s" , ntag.title);
	printf( "\n artiz: %s" , ntag.artist);
	printf( "\n album: %s" , ntag.album);

	getchar();
	return 0;

}
</pre>
</code>
</div>
<div>Kaynak : <a href="http://www.eksisozluk.com/show.asp?id=2960868" target="_blank">http://www.eksisozluk.com/show.asp?id=2960868</a></div>