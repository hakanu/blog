---
layout: post
title: Linux'ta Opera 10.50 alpha kurulumu
date: '2010-04-09 18:01:51'
---

Opera hastaları var aranızda görüyorum. 10.50 versiyonu Windows için çıktı. Ama Linux için kaç aydır ses seda yok ortalıkta. Niye yok şimdiye kadar hep Linux ve Windows sürümleri aynı anda çıkardı Opera'nın. Hemen söyliyim. Windows 7 ile birlikte Microsoft tarayıcı seçim ekranı çıkartıyor ya kullanıcıya Opera da yeni versiyonunu buna yetiştirmek için alelacele Windows sürümünü açıklarıyla sürdü. Haliyle hemen arkasına yama geldi 10.51 oldu. Onlar da haklı tabi. Opera 10.50 şu anda dünyanın en hızlı tarayıcısıymış. HTML5 ve CSS3 desteği var. Bunlar süpersonik teknolociler her ne kadar şu anda bunlarla yapılmış yaygın siteler olmasa da.

Linux için 10.50'nin alpha sı mevcut bunu kurmak için terminali açıp şu kodları sırasıyla yazıp çalışıtırıyoruz:

<strong><span style="color: #ff6600;">i386 kullanıcıları için:</span></strong>
<blockquote>wget http://snapshot.opera.com/unix/snapshot-6240/opera-10.50-6240.i386.linux.tar.bz2 -O - | tar xjf -</blockquote>
<blockquote>cd opera-10.50-6240.i386.linux/</blockquote>
<blockquote>./opera &amp;</blockquote>
<span style="color: #ff6600;"><strong>amd64 kullanıcıları için:</strong></span>
<blockquote>wget http://snapshot.opera.com/unix/snapshot-6240/opera-10.50-6240.x86_64.linux.tar.bz2 -O - | tar xjf -</blockquote>
<blockquote>cd opera-10.50-6240.x86_64.linux/</blockquote>
<blockquote>./opera &amp;</blockquote>