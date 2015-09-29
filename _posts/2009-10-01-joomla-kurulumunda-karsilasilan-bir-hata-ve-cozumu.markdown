---
layout: post
title: Joomla kurulumunda karşılaşılan bir hata ve çözümü
date: '2009-10-01 10:16:16'
---

Eğer herşeyiniz hazır ve adres çubuğuna http://localhost/joomla yazarak Joomla kurulumuna başladıysanız ilk kurulum sayfasının en üstünde şöyle bir hata alabilirsiniz:
<pre><strong>Deprecated</strong>:  Assigning the return value of new by reference is deprecated in 
<strong>C:\xampp\htdocs\joomla\libraries\pattemplate\patTemplate.php

</strong></pre>
Bunun sebebi büyük ihtimalle XAMPP'ın son versiyonu olan 1.7.2 kullanmanızdır. Çünkü bu XAMPP versiyonu PHP 5.3.0 içerir. Joomla ise şu anda PHP 5.3.0 ile çalışmak için onaylanmamıştır. Bu nedenle daha düşük bir XAMPP versiyonu kurarak sorun çözülebilir. Örneğin XAMPP 1.7.1 kurabilirsiniz. İndirmek için:

<a href="http://sourceforge.net/projects/xampp/files/">XAMPP 1.7.1 download</a>

Aynı şey WAMP için de geçerli olabilir. Çünkü onun da son versiyonunda PHP versiyonu 5.3.0. Onun da düşük versiyonu bulunarak sorun çözülebilir.
<pre><strong>
</strong></pre>