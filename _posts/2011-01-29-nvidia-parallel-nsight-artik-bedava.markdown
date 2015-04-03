---
layout: post
title: NVIDIA Parallel NSight artık bedava
date: '2011-01-29 01:18:50'
---

<a href="http://devdala.files.wordpress.com/2011/01/parallel_nsight_box_small.png"><img class="aligncenter" src="http://devdala.files.wordpress.com/2011/01/parallel_nsight_box_small.png" alt="" width="140" height="197" /></a>

CUDA şöyle iyi böyle iyi diye anlatıyor herkes de kimse paralel yazılım geliştirmenin zorluklarından bahsetmiyor. Bi kere paralel programlama zaten zor bişi de onu kenara koyarsak CUDA ayrı zor. Daha fazla kısıt var. Nvidia olabildiğince yardımcı olmaya çalışsa da daha gitmesi gereken çok yol var. En başta CUDA'da debug yok. Hadi canım diyenleri duyar gibiyim. Printf yok.-tu aslında. Artık yazdılar bi printf de onu kullanabiliyoruz ama o da bildiğimiz printf mantığıyla çalışmıyor ama hiç yoktan iyi.

Debug olayına dönersek tek ekran kartıyla debug yapmanız imkansız. Windows ortamı için konuşursak kesinlikle ekran kartı kernellerine giremiyoruz. Oralar bilinmez olarak kalıyor ama Visual Studio'dan hostta çalışan koda breakpoint koymak suretiyle o kısım ile ilgili debug yapılabiliyor. Linux'ta da gdb'ye eklenen cuda-gdb ile kısıtlı bir debug olanağı sağlanıyormuş. Bunu denemeye vaktim olmadı pek. En kısa zamanda deneyeceğim. Mac OS X'i bilmiyorum onlar zengin zaten alsınlar bi ekran kartı daha:p -bu esprinin açıklaması aşşada-

Şimdik NVIDIA developerlarını yalnız bırakmadı tabi ki ve Visual Studio üzerinde çalışan geliştiriciler için Parallel NSight diye bir plugin çıkarttı. Bunu kurup Visual Studio üzerinden kerneller debug edilebiliyor, breakpoint konabiliyor, belli bir zamanda ekran kartının belleği görüntülenip değişkenlerin değerlerine bakılabiliyor vs vs gibi büssürü süpersonik özelliği var eklentinin. Graphic Debug falan da var sanırım oraları bilmiyorum. Her neyse bunlar böyle güzel hoş özellikler de Parallel Nsight'in debug yapabilmesi için iki tane ekran kartına ihtiyacı var. Bu pek yazmıyor bi yerde de araştırınca biraz ortaya çıkıyor. Velhasıl kelam Nsight güzel bi yazılım. Videolarını şurdan bulabilirsiniz:

<a href="http://parallelnsight.nvidia.com/content/parallel-nsight-videos">http://parallelnsight.nvidia.com/content/parallel-nsight-videos</a>

Şu anda 1.51 sürümünde olan Nsight daha önceleri pro ve normal versiyon olarak çıkmıştı. Prosu paralıydı ama 60 günlüğüne-yanılıyor olabilirim- lisans veriyorlardı. İki gün önce toptan ücretsiz yapmışlar yazılımı. Çok da iyi olmuş.

İndirmek isteyenler şu tarafa gitti:

<a href="http://parallelnsight.nvidia.com/">http://parallelnsight.nvidia.com/</a>