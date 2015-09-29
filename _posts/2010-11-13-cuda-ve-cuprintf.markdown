---
layout: post
title: CUDA ve cuPrintf
date: '2010-11-13 21:33:29'
---

<a href="http://devdala.files.wordpress.com/2010/11/20080829_nvidia_logo.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2010/11/20080829_nvidia_logo.png" alt="" width="250" height="183" /></a>

cuPrintf  Nvidia'nın Nvidia Developer Account'a sahip insanların kullanımına sunduğu -nerdeyse- printf dengi fonksiyonu. Gerçekten süper bi olay. Kullanımı da oldukça basit. Tek yapılması gereken developer hesabından indirilen cuPrintf... isimli klasörün içindeki <strong>cuPrintf.cu</strong> ve <strong>cuPrintf.cuh</strong> dosyalarını projenin klasörünün içine atmak ve kendi projemizdeki kernelin üstüne<strong> #include "cuPrintf.cu</strong>" eklemek. Ve biter.

Nvidia'nın kendi örnek kodu şöyle:
<pre>#include "cuPrintf.cu"</pre>
<pre>__global__ void testKernel(int val)</pre>
<pre>{</pre>
<pre style="padding-left: 30px;">cuPrintf("Value is: %d\n", val);</pre>
<pre>}</pre>
<pre>int main()</pre>
<pre>{</pre>
<pre style="padding-left: 30px;">cudaPrintfInit();</pre>
<pre style="padding-left: 30px;">testKernel&lt;&lt;&lt;2, 3&gt;&gt;&gt;(10);</pre>
<pre style="padding-left: 30px;">cudaPrintfDisplay(stdout, true);</pre>
<pre style="padding-left: 30px;">cudaPrintfEnd();</pre>
<pre style="padding-left: 30px;">return 0;</pre>
<pre>}</pre>
<strong>cudaPrintfInit </strong>ve <strong>cudaPrintfEnd </strong>fonksiyonlarının proje boyunca sadece bir kez çağrılması yeterlidir. Çıktı doğrudan ekrana yazılmaz. Önce bufferda depolanır daha sonra <strong>cudaPrintfDisplay </strong>fonksiyonuyla ekrana basılır. Buffer size'i <strong>cudaPrintfInit</strong>(size_t bufferLen) fonksiyonuna opsiyonel olarak geçilen parametre ile değiştirilebilir.

<strong>cudaPrintfEnd </strong>fonksiyonu da cudaPrintfInit için ayrılan belleği free yapar. Yani sisteme geri verir.

Notnot: Sakın ha sakın gidip de projenin source klasörüne cuPrintf.cu'yu veya header klasörüne cuPrintf.cuh eklemeyin. Şöyle garip gurup hatalar verebilir:
<pre>
<blockquote>

<pre>cudaPrintfInit already defined in cuPrintf.cu.obj</pre>
</blockquote>
</pre>