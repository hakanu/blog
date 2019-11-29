---
published: true
layout: post
category: Debian
title: Free up space in debian server while apt-get commands are failing
---
This happened to me recently. Many resources online are all about "just clean your apt cache", "remove temporary files" etc. I was looking at a different problem which is "`Failed to write (No space left on device)`" during kernel update.

* Start by check the overall drive usage and see mounting points
	* `df -h` is your friend. If you lack space in / point, means its your normal disk you used for operations as user
* Do the usual stuff to open up some space
	* `sudo apt-get autoremove`
    * `sudo apt-get clean`
* Check top 10 largest folders
	* `du -a / | sort -n -r | head -n 10`
* Don't fully delete `/var/tmp`, just in case.
* `/var/logs` may have some culprit, delete the files which have .gz extension. Means they are already archieved. I'm assuming you don't need these logs. If you need, back up first.
* Remove unused packages:
	* `sudo apt-get remove packagename`
    * `sudo apt-get autoremove`
* Remove the kernels which are old. Before doing this check your version from `uname -a`. Don't try to remove your own kernel version.
	* `sudo apt-get remove --purge linux-image-4.11.0-XX-generic`

## More niche problems: what to do when all apt-get commands fail

Usually happpens in old servers due to accumulate kernel versions over time. I was running out of space in both / and /boot. Thanks to df -h I was able to see the root cause. I've had lots of kernel files in the /boot drive piled up over time which prevent the new one to be installed successfully and this hanging operation block all my apt-get commands due lack of the space. I can not do apt-get -f install or remove or anything. At the end I've found a safe way to delete old kernel files without breaking anything and freeing up some space in /boot

* Find which kernel version you are using: `uname -a`
* `cd /boot; ls -l`
* You will see that there are 4 different files for each suffix (something-4.4.0-145-generic)
* You can remove the ones which are older than your version (uname -a gives your version, don't remove that one, and one older and one newer just to stay in safe side.)
	* `rm /boot/*-4.4.0-145-generic`
* Once you removed all old kernel files, now you have breathing room.
* You can head back to the top of the post and apply normal stuff.
* Install missing kernel: `sudo apt-get install -f`
* Open up space: `sudo apt-get autoremove --purge`