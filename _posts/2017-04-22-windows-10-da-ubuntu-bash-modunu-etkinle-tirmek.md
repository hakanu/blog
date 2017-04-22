---
published: true
layout: post
category: windows
title: Windows 10'da Ubuntu Bash modunu etkinleştirmek
---
![](https://devdala.files.wordpress.com/2017/04/2.png)

Artık windows 10 ile beraber beta olarak ubuntu subsystem kullanabiliyoruz. Bu kesinlikle virtualbox ya da cygwin tarzı bi sanallaştırma değil daha native bir sistem. Uzun zamandır istenen bi özellikti ve sonunda Microsoft ekledi bunu. Aktifleştirmek çok kolay:

1.Başlat (Win) -> Ayarlar (Settings) -> Update & security

![](https://devdala.files.wordpress.com/2017/04/3.png)

2. Gelişitiricler (For developers) -> Use developer features -> Geliştirici modu (Developer mode)
3. Denetim masası (Control panel) -> Programlar (Programs) -> Turn on/off Windows features

![](https://devdala.files.wordpress.com/2017/04/4.png)

4. Yeniden başlat
5. İlk çalıştırmada bash.exe yi kendiniz tetiklemeniz lazım. Başlat -> bash yazıp çalıştırın
6. O sizi yönlendirecek ve bittiğinde artık başlat'a bash yazıp çalıştırabilirsiniz.

![](https://devdala.files.wordpress.com/2017/04/1.png)

7. gcc, apt-get, nano hemen hemen her şey var.
8. Hızlı bi gcc örneği
9. Dosyayı yarat

`touch hello.c`

10. İçine kodunu yaz:

`nano hello.c`

11. Aşağıdakini yapıştırın:

`/* Hello World program */

#include<stdio.h>

main()
{
    printf("Hello World");

}`

12. GCC'yi ubuntuya kurar gibi kur:

`sudo apt-get install gcc`

13. `gcc hello.c`
14. `./a.out`
15. "Hello world" basar.