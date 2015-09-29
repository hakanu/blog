---
layout: post
title: GWT from scratch tutorial - Hello World
date: '2012-01-28 01:51:14'
---

<div><a href="http://devdala.files.wordpress.com/2012/01/breaking-bad-season-3-episode-04-green-light-avi_20111031_204312-073.jpg"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/breaking-bad-season-3-episode-04-green-light-avi_20111031_204312-073.jpg" alt="" width="624" height="352" /></a></div>
<ul>
	<li>Eclipse -&gt; Help -&gt; Install New Software -&gt;</li>
</ul>
<p lang="en-US"><a href="http://dl.google.com/eclipse/plugin/3.7">http://dl.google.com/eclipse/plugin/3.7</a></p>

<ul>
	<li>Not necessary to select "android" package.</li>
	<li>At the end of the setup it is needed to restart Eclipse.</li>
	<li>New -&gt; Project -&gt; Google -&gt; Web Application Project</li>
</ul>
<p lang="en-US"><a href="http://devdala.files.wordpress.com/2012/01/gwt1.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwt1.png" alt="" width="519" height="674" /></a></p>

<h2>GwtDene1.java</h2>
<ul>
	<li>After clicking finish Eclipse creates a nice GWT app project. You can run it directly by clicking "Run" button in Eclipse. It is an awesome application that has both server and client. One problem-maybe it does not seem problem from another perspective:)- is that it is so advanced. I needed a "Hello World" project at the beginning.</li>
	<li>To create a Hello World project let's delete server and shared packages and their content and content of client package. We are gonna write from the start.</li>
	<li>Create a class in client package and give it a name. For me its "GwtDene1". Its content is like this:</li>
</ul>
<pre lang="java" line="1">package com.hakan.GwtDene1.client;

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
		Label label = new Label("Hello GWT !!!");
		Button button = new Button("Say something");
		button.addClickHandler(new ClickHandler() {
			@Override
			public void onClick(ClickEvent event) {
				Window.alert("Hello, again");
			}
		});
		RootPanel.get().add(label);
		RootPanel.get().add(button);
	}
}</pre>
<h2>GwtDene1.gwt.xml</h2>
<ul>
	<li>EntryPoint is a class which consists of the method to start application. This is similar to Java main method. EntryPoint is defined in gwt.xml. My EntryPoint class is "GwtDene1" then gwt.xml will be like this:</li>
</ul>
<code>
<pre lang="xml" line="1">
<?xml version="1.0" encoding="UTF-8"?>
<module rename-to='gwtdene1'>
	<inherits name='com.google.gwt.user.User' />
	<inherits name='com.google.gwt.user.theme.standard.Standard' />
	<entry-point class='com.hakan.GwtDene1.client.GwtDene1' />
</module>

</pre>
</code>
<pre></pre>
<h2 lang="en-US">GwtDene1.html</h2>
<ul>
	<li>We are needed to edit the html file which is under war folder. This is actually the page we will see after opening the site. The output of our GWT app's javascript code is put in this html. The important part is showing the js in this html file correctly.</li>
</ul>
<ul>
	<li>You need to be careful about js file path. It is case sensitive!</li>
</ul>
<code>
<pre lang="html4strict" line="1">
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<link type="text/css" rel="stylesheet" href="GwtDene1.css">
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
<ul>
	<li>This is optional. You can change the style.</li>
</ul>
</ul>
<ul>
	<li>Check this class names out!</li>
</ul>
<code>
<pre lang="css" line="1">
.gwt-Label {

color: #DF0101;

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
<ul>
	<li>This is the operation for identifying GwtDene1.html as welcome file of the app to the servlet.</li>
</ul>
</ul>
<code>
<pre lang="xml" line="1">
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee 
              http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
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
	<li>After clicking on "Run" on eclipse, there appears an address like this one below. Open this in Chrome. It will want to install a GWT extension. Let it go.</li>
</ul>
<div><a href="http://devdala.files.wordpress.com/2012/01/gwtrun.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwtrun.png" alt="" width="385" height="219" /></a></div>
<div></div>
<div>The coolest part is that i dont need to run the application again and again after editing the code. The browser is in a relationship with the source code. after saving the changes in eclipse, you can refresh the browser tab and see the changes. Cool!</div>
<h1>GWT Designer setup</h1>
Eclipse -&gt; Install New Software -&gt;
<p lang="en-US"><a href="http://dl.google.com/eclipse/inst/d2gwt/latest/3.7">http://dl.google.com/eclipse/inst/d2gwt/latest/3.7</a></p>
<p lang="en-US">Here is an screeshot from GWT Designer.</p>
<p lang="en-US"><a href="http://devdala.files.wordpress.com/2012/01/gwtdesigner.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2012/01/gwtdesigner.png" alt="" width="726" height="473" /></a></p>

<ul>
	<li>Complete code can be downloaded from here.</li>
</ul>
<p lang="en-US"><a href="http://dl.dropbox.com/u/3600380/Projeler/Gwt/GwtDene1.zip" target="_blank">http://dl.dropbox.com/u/3600380/Projeler/Gwt/GwtDene1.zip</a></p>