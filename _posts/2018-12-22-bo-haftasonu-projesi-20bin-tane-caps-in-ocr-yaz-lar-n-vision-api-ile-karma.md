---
published: true
layout: post
category: python
title: >-
  Boş haftasonu projesi: 20bin tane caps'in OCR yazılarını Vision API ile
  çıkarma
---
![](https://devdala.files.wordpress.com/2018/12/Screenshot-2018-12-22-at-11.31.57-PM.png)

Yine gereksiz bir projeyle burdayım. Uzun zamandır aklımdaydı, dost mecliselerinde aradığım capsleri ve karikatürleri tekrar bulmak çok zor oluyordu.
Instagram zaten çok aramacanlısı değil. O yüzden hazır elimin altında bulunan [guldum.net](https://guldum.net)'teki 39bin civarı capsi [Vision API](https://cloud.google.com/vision/)'dan geçirip OCR (optical character recogniton) yazılarını çıkarmaya karar verdim. Müthiş boş haftasonu projesi fikirlerimi listelesem Alan Turing mezarında ters döner.

# Önbilgi

[Guldum.net](https://guldum.net) benim hobi projelerimden biri. Sağda solda gördüğüm, güldüğüm caps, karikatür ve videoları atıyorum. Sonraları minik captionlar yazmaya başladım. Sonra baya baya arama trafiği gelmeye başladı ve cidden yalnız olmadığımı farkettim. Bu olaya biraz daha otomasyon katıp neden mini bir caps ve karikatür arama motorumuz olmasın diye yola çıktım. Şu an neredeyse 40bin post var sitede.

# Kurulum

```
# Install virtualenv first.
pip install virtualenv --user

# Initialize the virtual environment.
virtualenv env
source env/bin/activate

# Install the deps.
echo "google-cloud-vision==0.35.0" > requirements.txt
pip install -r requirements.txt
```

# Script

```
from google.cloud import vision
from google.cloud.vision import types

def GetCloudOcrFromBytes(content):
  client = vision.ImageAnnotatorClient()
  image = types.Image(content=content)
  response = client.text_detection(image=image)
  texts = response.text_annotations
  if len(texts) > 0 :
    return texts[0].description
  return ''
```

# Sonuçlar

Vision API Bilgisayar yazılarında çok başarılı ki capslerin çoğu twitter screenshot'ı olduğu için sonuçlar minimum modifikasyon gerektiriyor.

Karikatür arama motoru asıl amacım olsa da hiç bir API güzel sonuç veremedi benim denemelerimde. Sebebi karikatürlerin font tipi garipliği, font kerning boyutu ve konuşma balonlarının sırasının algılanmasının zorluğu diye tahmin ediyorum.

Türkçe spell checking ve auto correct ile ilgili pek düzgün kütüphaneler bulamadım. Şu ara bi corpus yaratıp Peter Novig reyisin tekniklerini ([How to write a spelling corrector](https://norvig.com/spell-correct.html)) kendi spell checkerimi yazmak istiyorum. Bu OCR sonuçlarını spell checkerdan geçirsem bi tık daha güzel olur belki.

Bu arada tabi ki Vision API ile beraber imajları açık kaynak kodlu [Tessaract OCR](https://github.com/tesseract-ocr/)'dan da geçirdim. Türkçe'de pek güzel sonuçlar veremedi benim denemelerimde. Çok fazla gürültülüydü sonuçlar. En azından ben Türkçe'ye bağlıyorum.

## Başarılı örnek

https://guldum.net/post/180915250803/peteremre-peterbishoppp-takip-et-%C5%9Fu-an-12

![](https://devdala.files.wordpress.com/2018/12/Screenshot-2018-12-22-at-11.07.06-PM.png)

## Başarısız örnek

![](https://devdala.files.wordpress.com/2018/12/Screenshot-2018-12-22-at-11.09.10-PM.png)


## Linkler

* https://github.com/GoogleCloudPlatform/cloud-vision/tree/master/python
* https://github.com/tesseract-ocr/
* https://guldum.net
* https://www.instagram.com/guldum_net/