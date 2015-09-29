---
layout: post
title: Flex'te event oluşturma
date: '2010-07-28 21:15:33'
---

Flex'te script tagi açıp java c yazar gibi araya kodlar serpiştirebiliyoruz. Netekim event yönetimi de bu şekilde işliyor.

Önce listeneri butona ekliyoruz. Arkasına listenerin handlerini tanımlıyoruz. Burda bi messagebox çıkıyor şimdilik.

[php]&lt;fx:Script&gt;
 &lt;![CDATA[
 import mx.controls.Alert;

 private function initApp():void {
    button1.addEventListener(MouseEvent.CLICK, myEventHandler);
 }

 private function myEventHandler(event:Event):void {
     Alert.show(&quot;Olay oldu&quot;);
 }

 ]]&gt;
 &lt;/fx:Script&gt;[/php]

Butonu da şu şekilde tanımlamak makbul tabi ki:

[php]&lt;/pre&gt;
&lt;s:Button x=&quot;23&quot; y=&quot;238&quot; label=&quot;Home&quot; click=&quot;myEventHandler(event)&quot; id=&quot;button1&quot;/&gt;
&lt;pre&gt;[/php]