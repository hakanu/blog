---
published: true
layout: post
category: linux
title: 'Viewing HEIF (HEIC) images on arch linux #manjaro'
---
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Wondering if HEIC/F image format brings anything extra apart from smaller size.<br>After installing a million packages on PC:<br>- Some HEIF images are not thumbnailed<br>- Some HEIF images are thumbnailed but can not be viewed<br>- Can not be transferred over messaging apps, need to convert</p>&mdash; Hakan Uysal (@hakanu_) <a href="https://twitter.com/hakanu_/status/1411960253000962052?ref_src=twsrc%5Etfw">July 5, 2021</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Although 17% market share of iPhone and its default image format [HEIF (High Efficiency Image File Format)](https://en.wikipedia.org/wiki/High_Efficiency_Image_File_Format) which is occupying less space for arguably same quality images; we still don't have proper support for HEIF/HEIC/HEIVC in any of the operating systems except Mac OS X and its weird Photos app which is extremely user unfriendly.

![](https://www.counterpointresearch.com/wp-content/uploads/2021/02/Counterpoint-Research-Global-Smartphone-Shipments-Market-Share-2018-Q1-2021-Q1.png)

I've found [Viewnior](https://github.com/hellosiyan/Viewnior) which is able to open them and quicker than opening GIMP every time.

For command line interface, you can use `libheif`

```bash
# For viewing
sudo pacman -S viewnior

# For CLI tools for dealing with HEIF HEIC formatted images and videos through terminal.
# eg. bulk convert them etc.
sudo pacman -S libheif

# Now let's use it.
heif-convert image.heic image.jpg

# OR, good old ffmpeg
ffmpeg -i image.heic image.jpg
```

I've still not found a method to generate the thumbnails automatically though. I pulled this off in Ubuntu but tumbler or heifthumbnailer etc are not working. Let's see.

