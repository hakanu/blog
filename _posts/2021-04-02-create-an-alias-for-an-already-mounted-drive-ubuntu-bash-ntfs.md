---
published: true
layout: post
category: bash
title: 'Create an alias for an already mounted drive #ubuntu #bash #ntfs'
---

Create an alias (symlink, symbolic link) from an already mounted drive to a folder.
Recently I have moved to ubuntu from WSL2 where windows introduces NTFS drives as /c, /d, /e meanwhile ubuntu is mounting them as `/home/$user/media/foo`.  

First I tried to mount second time onto /d:
* Create the folder to be aliased on: `sudo mkdir /d`
* Grab the drive mount path.: `df -h`
* `sudo mount /dev/sdb1 /d`
	* Error: `Mount is denied because the NTFS volume is already exclusively opened. The volume may be already mounted, or another software may use it which could be identified for example by the help of the 'fuser' command.`
   	* This suggests that I should not re-mount, instead I can create a symlink.
 * Try this: `sudo ln -s /media/$user/$drive_name/* /e`
 	* Gotcha: Need to use this: `/*`, otherwise you had to do `/e/$drive_name/sub_folder` instead of directly `/e/sub_folder`
 * voila: `ls /e` => see the full contents and use as if it's normal path.