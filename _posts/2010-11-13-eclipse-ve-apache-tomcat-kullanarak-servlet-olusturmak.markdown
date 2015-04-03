---
layout: post
title: Eclipse ve Apache Tomcat kullanarak servlet oluşturmak
date: '2010-11-13 21:13:34'
---

Eclipse Helios versiyonuyla bu iş iyice kolaylaşmış ama benim gibi bilmeyince insan zor oluyor tabi.
<ul type="disc">
	<li>Eclipse JAVA EE      Developers versiyonu indirilir</li>
</ul>
<p style="padding-left: 30px;">En büyük boyutlu olan zaten:</p>
<p style="padding-left: 30px;"><a href="http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/heliossr1" target="_blank">Download Eclipse for Java EE Developers</a></p>

<ul type="disc">
	<li>Eclipse açılıp File -&gt; New -&gt;      Project -&gt; Dynamic Web Project denir.</li>
	<li>Adı koyulur projenin,      Dynamic Web Module Version 3.0 işaretlidir. O 2.5 yapılır. Çünkü      Apache Tomcat 6.0 ile 3.0 uyumlu değil. O şekilde devam edilirse hata verecektir zaten. Apache Tomcat 7.0 uyumlu ama o da      Web 3.0 içinmiş bildiğim kadarıyla.</li>
</ul>
<a href="http://devdala.files.wordpress.com/2010/10/eclipse-apache-2.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/eclipse-apache-2.jpg" alt="" width="424" height="500" /></a>
<ul type="disc">
	<li>Projeyi yarattıktan      sonra Run -&gt; Run on server denir. Ordan Apache Tomcat 6.0 seçilir.      Path ister. Oraya da bi path yazıp Download and Install'a basılır.      Arka planda yükleme yapacak, bitene kadar beklenir. Bitince next aktifleşecek.</li>
</ul>
<a href="http://devdala.files.wordpress.com/2010/10/eclipse-apache-3.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/eclipse-apache-3.jpg" alt="" width="491" height="147" /></a>
<p style="text-align: center;"><a href="http://devdala.files.wordpress.com/2010/10/eclipse-apache-4.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/eclipse-apache-4.jpg" alt="" width="366" height="454" /></a></p>

<ul type="disc">
	<li>Artık server hazır.      Direk run diyip çalıştırılabilir. Sıra geldi servlet yaratmaya.</li>
	<li>New -&gt; Servlet      dedikten sonra HttpServlet'ten tut da her şey hata verecek. Henüz servlet      jarını import etmedik çünkü.</li>
</ul>
<p style="padding-left: 30px;">Şöyle bir hata olması kuvvetle muhtemel hatta capsli:</p>

<blockquote>
<pre>HttpServlet cannot be resolved to a type
<a href="http://devdala.files.wordpress.com/2010/10/eclipse-apache-1.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/10/eclipse-apache-1.jpg" alt="" width="561" height="210" /></a></pre>
</blockquote>
<ul type="disc">
	<li>Projeye sağ tıklayıp      Build Path -&gt; Configure Build Path diyoruz.</li>
	<li>Ordan sağdaki      sekmelerden Libraries'e basıyoruz. Add External JARs basıyoruz. Ordan da      Apache Tomcat 6.0'ı yüklediğimiz pathe gidiyoruz. O klasörün altında lib      diye bi klasör daha olmalı. Ona basıyoruz. Ordan da "servlet-api.jar" var onu seçiyoruz.</li>
	<li>OK diyip kapatıyoruz.      Tada artık servlet hazır.</li>
</ul>
Yukarıdakilerin hepsi Eclipse tabanlı bir geliştirme ortamı olan IBM Rational Application Developer için de aynen geçerlidir. Hatta Helios için download and install diyip kurulan Apache Tomcat 6.0 onun için de aynı path ile tekrar indirmeye gerek kalmaksızın kullanılabilir.

Notnot: Bu yöntemi ben deneme yanılma yoluyla buldum daha iyi bir yöntem bilen varsa link falan verirse sevinirim.