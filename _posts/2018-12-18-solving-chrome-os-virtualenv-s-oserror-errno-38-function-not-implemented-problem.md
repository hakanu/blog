---
published: true
layout: post
category: python
title: >-
  Solving Chrome OS virtualenv's "oserror errno 38 function not implemented"
  problem
---
If you use ChromeOS' native shell, you may encounter this problem.

When you run this:
`virtualenv ENV`

You may occasionally get this.
```
Traceback (most recent call last):
  File "/usr/local/bin/virtualenv", line 11, in <module>
    sys.exit(main())
  File "/usr/local/lib/python2.7/site-packages/virtualenv.py", line 713, in main
    symlink=options.symlink)
  File "/usr/local/lib/python2.7/site-packages/virtualenv.py", line 925, in create_environment
    site_packages=site_packages, clear=clear, symlink=symlink))
  File "/usr/local/lib/python2.7/site-packages/virtualenv.py", line 1111, in install_python
    fix_lib64(lib_dir, symlink)
  File "/usr/local/lib/python2.7/site-packages/virtualenv.py", line 1541, in fix_lib64
    os.symlink('lib', lib64_link)
OSError: [Errno 38] Function not implemented
```

`/usr/local/bin/python: error while loading shared libraries: libpython2.7.so.1.0: cannot open shared object file: No such file or directory`

As far as I understand this happens due to the drive mounting issue.

This is optional step:
`sudo mount -i -o remount,exec /home/chronos/user/`

Run virtualenv ENV from home folder:
`cd;virtualenv ENV`
`source /path/to/ENV/bin/activate`