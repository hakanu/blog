---
published: true
layout: post
category: windows
title: Windows 10'da Ubuntu Bash modunu etkinleştirmek
---
![](https://devdala.files.wordpress.com/2017/04/2.png)

Artık windows 10 ile beraber beta olarak ubuntu subsystem kullanabiliyoruz. Bu kesinlikle virtualbox ya da cygwin tarzı bi sanallaştırma değil daha native bir sistem. Uzun zamandır istenen bi özellikti ve sonunda Microsoft ekledi bunu. Aktifleştirmek çok kolay:

- Başlat (Win) -> Ayarlar (Settings) -> Update & security

![](https://devdala.files.wordpress.com/2017/04/3.png)

- Gelişitiricler (For developers) -> Use developer features -> Geliştirici modu (Developer mode)
- Denetim masası (Control panel) -> Programlar (Programs) -> Turn on/off Windows features

![](https://devdala.files.wordpress.com/2017/04/4.png)

- Yeniden başlat
- İlk çalıştırmada bash.exe yi kendiniz tetiklemeniz lazım. Başlat -> bash yazıp çalıştırın
- O sizi yönlendirecek ve bittiğinde artık başlat'a bash yazıp çalıştırabilirsiniz.

![](https://devdala.files.wordpress.com/2017/04/1.png)

- gcc, apt-get, nano hemen hemen her şey var.
- Hızlı bi gcc örneği
- Dosyayı yarat

`touch hello.c`

- İçine kodunu yaz:

`nano hello.c`

- Aşağıdakini yapıştırın:

```
/* Hello World program */

#include<stdio.h>

main()
{
    printf("Hello World");

}
```

- GCC'yi ubuntuya kurar gibi kur:

`sudo apt-get install gcc`

- `gcc hello.c`
- `./a.out`
- "Hello world" basar.