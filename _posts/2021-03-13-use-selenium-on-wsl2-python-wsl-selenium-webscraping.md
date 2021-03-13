---
published: true
layout: post
category: python
title: 'Use Selenium on WSL2 #python #wsl #selenium #webscraping'
---
---
published: true
layout: post
category: python
title: 'Use Selenium on WSL2 with python'
---

This has been a pain for so long. Finally I was able to pull it off. Only tricky part was the windows firewall apparently.

Couldn't make it work with chromedriver though. If you really want to use chromedriver, you can try running it from windows python rather than wsl python.

1. WSL2 setup (Windows Subsystem for Linux, WSL Ubuntu works well for me): https://docs.microsoft.com/en-gb/windows/wsl/install-win10

1. Install firefox

```bash
sudo apt install firefox
# Taken from https://blog.henrypoon.com/blog/2020/09/27/running-selenium-webdriver-on-wsl2/
export DISPLAY=$(ip route | awk '{print $3; exit}'):0
```

1. Install VcXsrv Windows X Server to be able to create windows from wsl2. https://sourceforge.net/projects/vcxsrv/

1. Install geckodriver: https://github.com/mozilla/geckodriver/releases

1. Go to:
Control Panel -> System and Security -> Windows Defender Firewall

![](https://devdala.files.wordpress.com/2021/03/screenshot-2021-03-13-151908.jpg)

1. Click on:
Allow an app or feature through Windows Defender Firewall

1. Find VcXsrv windows xserver from the list. Enable private (and public if your computer is not exposed to public).

![](https://devdala.files.wordpress.com/2021/03/screenshot-2021-03-13-152012.jpg)

1. Run VcXsrv

```bat
& 'C:\Program Files\VcXsrv\xlaunch.exe' -ac
```

1. Example python snippet to try geckodriver:

```python
import time

from selenium import webdriver
from selenium.webdriver import DesiredCapabilities
from selenium.webdriver.firefox.options import Options


print('Setting the capabilities')
capabilities = DesiredCapabilities.FIREFOX
capabilities["marionette"] = True
firefox_bin = "/usr/bin/firefox"

options = Options()
options.headless = False  # If you want to enable headless mode.

browser = webdriver.Firefox(
    firefox_binary=firefox_bin, capabilities=capabilities, options=options)

print('opening the page', browser)
browser.get("https://hakanu.com/")
html = browser.page_source
print('returned html size: ', len(html))
open('gecko_test_wsl.html', 'w').write(html)  # See the html if you want.

time.sleep(10)

browser.close()
```

![](https://devdala.files.wordpress.com/2021/03/screenshot-2021-03-13-152207.jpg)