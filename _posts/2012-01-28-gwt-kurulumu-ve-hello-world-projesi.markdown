---
layout: post
title: GWT Kurulumu ve hello world projesi
date: '2012-01-28 01:39:42'
---

<div><a href="http://devdala.files.wordpress.com/2012/01/finding-nemo-hd-m4v_20110903_210308-997.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/finding-nemo-hd-m4v_20110903_210308-997.jpg" alt="" width="896" height="504" /></a></div>
<div>GWT, java yazarak javascript applicationlar olusturmaya olanak veren sahane bir framework. Kurulum soyle:</div>
<ul>
	<li>Eclipse -&gt; Help -&gt; Install New Software -&gt; <a href="http://dl.google.com/eclipse/plugin/3.7">http://dl.google.com/eclipse/plugin/3.7</a></li>
</ul>
<ul>
	<li>Android pakedi secilmeyebilir. Kurulum bittikten sonra eclipse kendine restart atmak ister.</li>
	<li>New -&gt; Project -&gt; Google -&gt; Web Application Project</li>
</ul>
<p lang="en-US"><a href="http://devdala.files.wordpress.com/2012/01/gwt1.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwt1.png" alt="" width="519" height="674" /></a></p>

<h2>GwtDene1.java</h2>
<ul>
	<li>Finish dedikten sonra eclipse bize kendisi guzel bir gwt application yaratir. Direk run diyip cikti incelenebilir. Serverli clientli on numara bir application kendisi. Yalniz bir kusuru var ki o da  cok ileri duzey olmasi. Tabi ki ileri duzey diyince yanlis anlasilmasin yeni baslayanlar icin ileri duzey. Basit bir hello world projesi yaratamiyoruz. En azindan ben beceremedim. Birkac yerde okudugum uzre de bunun icin sikayette bulunmuslar gugila.</li>
	<li>Neyse ben temiz basit bir hello world projesi istiyordum onun icin: proje agacindan server package'inin ve shared package'inin tamamini ve client package'nin icerigini silinir tamamen. Temelden alinir. Client pakedinin icine yeni bir class yaratalir ve adina GwtDene1 dedim. Icerigi asagidaki gibidir:</li>
</ul>
<code>
<pre lang="java" line="1">
package com.hakan.GwtDene1.client;

import com.google.gwt.core.client.EntryPoint;

import com.google.gwt.event.dom.client.ClickEvent;

import com.google.gwt.event.dom.client.ClickHandler;

import com.google.gwt.user.client.Window;

import com.google.gwt.user.client.ui.Button;

import com.google.gwt.user.client.ui.Label;

import com.google.gwt.user.client.ui.RootPanel;

public class GwtDene1 implements EntryPoint {

@Override

public void onModuleLoad() {

Label label = new Label("Heyow");

Button button = new Button("Buton bu");

button.addClickHandler(new ClickHandler() {

@Override

public void onClick(ClickEvent event) {

Window.alert("Blog on numero");

}

});

RootPanel.get().add(label);

RootPanel.get().add(button);

}

}

</pre>
</code>
<h2>GwtDene1.gwt.xml</h2>
<ul>
	<li>EntryPoint belirlenmesi lazim. Java'da bulunan main methodu gibi entrypoint de applicationin nerden baslayacagini tanimlar. Onu gwt xmlinde tanimlanir. Soyle ki benim EntryPointim az onceki GwtDene1 classi idi. Onu xml'e asagidaki gibi yaziyorum:</li>
</ul>
<code>
<pre lang="xml" line="1">
<?xml version="1.0" encoding="UTF-8"?>

<module rename-to='gwtdene1'>

<inherits name='com.google.gwt.user.User'/>

<inherits name='com.google.gwt.user.theme.standard.Standard'/>

<entry-point class='com.hakan.GwtDene1.client.GwtDene1'/>

</module>
</pre>
</code>
<h2 lang="en-US">GwtDene1.html</h2>
<ul>
	<li>War klasorunun altindaki sayfanin goruntulenecegi xml'in icerigini de duzenlemek gerekiyor. Bu gorecegimiz sayfa aslinda. Gwt'nin ciktisi olan javascript kodu da bu html icinden gosterilir. Burda onemli olan o js dosyasinin duzgun olarak html'de gosterilmesidir. Buyuk kucuk harfe dikkat etmek lazim. html affetmez.</li>
</ul>
<code>
<pre lang="html4strict" line="1">
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">

<html>

<head>

<meta http-equiv="content-type" content="text/html; charset=UTF-8">

<link type="text/css" rel="stylesheet"

href="GwtDene1.css">

<title>My First GWT application</title>

<script type="text/javascript" language="javascript"

src="gwtdene1/gwtdene1.nocache.js"></script>

</head>

<body>

<!-- OPTIONAL: include this if you want history support -->

<iframe src="javascript:''" id="__gwt_historyFrame" tabIndex='-1'

style="position: absolute; width: 0; height: 0; border: 0"></iframe>

<h1>My First GWT application</h1>

</body>

</html>

</pre>
</code>
<h2 lang="en-US">GwtDene1.css</h2>
<ul>
	<li>Css ile de oynanabilir istek dahilinde.</li>
</ul>
<code>
<pre lang="css" line="1">
.gwt-Label {
font: normal 12px tahoma, arial, helvetica, sans-serif;

border: 1px solid black;

}

.gwt-Button {

font-size: 12px;

font-family: arial, sans-serif;

}
</pre>
</code>
<h2 lang="en-US">web.xml</h2>
<ul>
	<li>Servlete welcome file inin GwtDene1.html oldugunun gosterilmesi operasyonu bu da.</li>
</ul>
<code>
<pre lang="xml" line="1">
<?xml version="1.0" encoding="UTF-8"?>

<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation="http://java.sun.com/xml/ns/javaee

<a href="http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd</a>"

version="2.5"

xmlns="http://java.sun.com/xml/ns/javaee">

<!-- Servlets -->

<!-- Default page to serve -->

<welcome-file-list>

<welcome-file>GwtDene1.html</welcome-file>

</welcome-file-list>

</web-app>

</pre>
</code>
<ul>
	<li>Run diyince asagidaki gwt console unda soyle bir adres gorunur. Bu adres chrome'da acilir. Chrome bi eklenti yuklemek ister. Let it go. Yuklesin.</li>
</ul>
<div><a href="http://devdala.files.wordpress.com/2012/01/gwtrun.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwtrun.png" alt="" width="385" height="219" /></a></div>
<h1>GWT Designer kurulumu</h1>
Eclipse -&gt; Install New Software -&gt; <a href="http://dl.google.com/eclipse/inst/d2gwt/latest/3.7">http://dl.google.com/eclipse/inst/d2gwt/latest/3.7</a>
<p lang="en-US">Designer paleti soyle gorunuyor:</p>
<p style="text-align: center;" lang="en-US"><a href="http://devdala.files.wordpress.com/2012/01/gwtdesigner.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwtdesigner.png" alt="" width="726" height="473" /></a></p>

<ul>
	<li>Kodun tamaminin surdan indirilmesine:</li>
</ul>
<p style="text-align: left;" lang="en-US"><span style="text-align: center;"><a href="http://dl.dropbox.com/u/3600380/Projeler/Gwt/GwtDene1.zip" target="_blank">http://dl.dropbox.com/u/3600380/Projeler/Gwt/GwtDene1.zip</a></span></p>