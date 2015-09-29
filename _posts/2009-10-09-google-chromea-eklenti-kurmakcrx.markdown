---
layout: post
title: Google Chrome'a eklenti kurmak[CRX]
date: '2009-10-09 06:53:23'
---

Not: Bu yazı Chrome 4 versiyonu çıkmadan önce yazılmıştır. Chrome 4 ile birlikte "extension"(uzantı) adı altında chrome'a eklenti kurulabilmektedir. Eğer ki eski bir Chrome kullanıcısıysanız bunları yapabilirsiniz. Chrome 4+ kullanıyorsanız da şuradan eklenti indirebilirsiniz:

<a href="https://chrome.google.com/extensions">Google Chrome Extensions</a>

Chrome'a da eklenti kurulabilir tabi ki Firefox kadar geniş bir yelpazede olmasa da. Bunun için şöyle bir yol izlemelisiniz:

1. Öncelikle Chrome'un geliştiriciler için olan versiyonunu indiriniz. Şu taraftan:

<a href="http://www.google.com/chrome/eula.html?extra=devchannel">Download Google Chrome Developers Version</a>

2. Chrome'un bu versiyonunu kurduktan sonra masaüstündeki kısayola sağ tıklayıp "Özellikler"e girilir

3. "Hedef" yazan kısmın sonuna şu eklenir.
<pre><strong><code>--enable-extensions
</code></strong></pre>
<code>Şöyle bir görüntü oluşmalıdır:</code>

<strong> </strong>
<pre>
<pre><strong><code>'C:\Documents and Settings\%Your Username%\Local Settings\Application Data\Google\Chrome\Application\chrome.exe' --enable-extensions
</code></strong><strong> </strong></pre>
</pre>
4. Chrome'u açın ve şuradan <strong>CRX </strong>uzantılı bir eklenti olan <strong>Gmail Checker</strong> eklentisini indirin:

<a href="https://dl-ssl.google.com/chrome/extensions/gmail.crx" target="_blank">Download Gmail Checker(gmail.crx)</a>

5. Kurulumu onaylama kutusu gelecektir. Onaylayınız.

6. Kurulumun ardından Gmail Checker çalışacaktır. Herhangi bir yeniden başlatmaya ihtiyaç yoktur.

Diğer ilgili yazı ise:

<a href="http://devdala.wordpress.com/2009/08/29/google-chromea-greasemonkey-scriptleri-eklemek/" target="_blank">Google Chrome'a greasemonkey scriptleri eklemek</a>