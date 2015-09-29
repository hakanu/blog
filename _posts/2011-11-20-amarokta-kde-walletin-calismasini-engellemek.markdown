---
layout: post
title: Amarok'ta KDE wallet'in calismasini engellemek
date: '2011-11-20 16:33:53'
---

Gnome'da kde zaten sikintili. bi de bu tip ozellesmis uygulamalar gelince iyice sikinti oluyor. Amarok kullananlar bilir acilista takilip kalir falan.

Onu engellemek icin amarok'u acinca Settings -&gt; Configure Amarok -&gt; Internet Services geliyoruz. Last.fm'in basindaki tiki kaldiriyoruz. Ben de calismadi bi daha wallet service. Ama olmazsa su da yapilabilir:

- Last.fm disable edildikten sonra amarok kapatilip terminale su yazilir:
<pre>gedit .kde/share/config/amarokrc</pre>
- Sonra asagidaki deger yes yapilir
<pre>ignoreWallet=yes</pre>
- Sordugu zaman da acces always diyiniz.