---
published: false
layout: post
category: Debian
title: Free up space in debian server while apt-get commands are failing
---
This happened to me recently. Many resources online are all about "just clean your apt cache", "remove temporary files" etc. I was looking at a different problem which is "`Failed to write (No space left on device)`".

* Start by check the overall drive usage and see mounting points
	* df -h
    	* if you lack space in / point, means its your normal disk you used for operations as user
* 

## More niche problems: what to do when all apt-get commands fail

Usually happpens in old servers.

sudo apt-get remove --purge linux-image-3.11.0-XX-generic
sudo apt-get install -f # Installs the kernel
sudo apt-get autoremove

