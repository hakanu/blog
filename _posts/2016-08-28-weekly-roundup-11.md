---
published: false
layout: post
category: roundup
title: 'Weekly roundup - 11 '
---

* Wordpress released .blog extension, get yours with an incredible price.
	* eg. hakan.blog -> 5220 euro, thanks, feeling valued.
	* <https://get.blog/>
* Get Android debug keystore hash (SHA1, SHA256 or MD5) - useful for firebase authentication:

`keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android`

* Star Citizen 2016 - Gamescom trailer: <https://www.youtube.com/watch?v=GucYhhLwIxg>

* Android Nougat 7.0
	* [Official website](https://www.android.com/versions/nougat-7-0/)
    * [TheVerge review](http://www.theverge.com/2016/8/22/12578946/android-7-nougat-review-nexus)
* Yet another betalist clone: <http://www.betafy.co/>
* I needed a Mac's Preview like image editor to quickly resize/stretch images for Chrome Webstore. I made my logo but it turned out to be 128x127px so I need to make it 128x128px. Spent like 15 minutes. Tried these ones:
	* Geeqie
    	* `sudo apt-get install geeqie`
    * Gthumb
    	* `sudo apt-get install gthumb`
    * Shotwell image viewer
    * Nautilus right click context menu resizer
    	* `sudo apt-get install phatch`
    * Phatch
    	* `sudo apt-get install phatch`
    * Finally imagemagick - worked terminal <3
    	
        ```bash
        sudo apt-get install imagemagick
    	mogrify -resize 128x128! logo.png # ignore image aspect ratio
    	mogrify -resize 50% *png      # keep image aspect ratio
		mogrify -resize 320x240 *png  # keep image aspect ratio
		mogrify -resize 320x240! *png # ignore image aspect ratio
		mogrify -resize x240 *png     # ignore image aspect ratio
  		mogrify -resize 320x *png     # ignore image aspect ratio
        ```

    * If I was using Windows, Id just go for this [one, amazing app with lib code from Tony](http://www.codeproject.com/Articles/3603/Classes-to-read-and-write-BMP-JPEG-and-JPEG) 

* [What is the difference?](http://stackoverflow.com/questions/4911820/percent-encoding-javascript)
	* encodeURI is just for escaping URLs
    * encodeURIComponent also escapes = and &
    * escape works differently with non-ASCII unicode symbols
