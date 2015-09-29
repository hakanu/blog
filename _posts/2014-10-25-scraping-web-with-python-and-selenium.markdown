---
layout: post
title: Scraping web with python and selenium
date: '2014-10-25 22:32:45'
---

[![](http://distilleryimage4.ak.instagram.com/578775c0ad4e11e382961290f642fb88_8.jpg)](http://instagram.com/uhakan)

A couple of weeks ago, I had a need to parse some parts of some web page. It was a page whose main content is loaded after finishing the GET request to the page. This means that python's **urllib**, **urllib2** and **requests** packages will fail to download the exact same source as your Chrome renders when you reach the site via browser (not programmatically). Because url libraries usually return the content after GET request finishes, they don't wait until all of the ajax calls finish. This causes discrepancy between fetched code and rendered code. In my case, I needed the rendered code. After long investigation and [asking out in StackOverflow](http://stackoverflow.com/questions/25734467/how-to-get-source-url-of-dynamically-created-flash-videos-by-javascript) (nobody replied and question is deleted), I ended up using Selenium to emulate normal browser behaviour. It was kinda hard for me because I need async flash content and firefox driver (default driver) of Selenium is not capable of rendering flash content. I switched to Chrome driver. This step just made things harder.

## Prereqs

* Install [PhantomJS](http://phantomjs.org/download.html)
* `sudo easy_install selenium`
* `sudo easy_install pyvirtualdisplay`
* `sudo apt-get install xvfb`
* Firefox and phantomjs are not capable of showing the flash videos. Chrome is the only successful one.
* [Install chrome](http://www.howopensource.com/2011/10/install-google-chrome-in-ubuntu-11-10-11-04-10-10-10-04/)

 * `wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -`
 * `sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'`
 * `sudo apt-get update`
 * `sudo apt-get install google-chrome-stable`
* Chrome driver
http://chromedriver.storage.googleapis.com/index.html

 * `wget http://chromedriver.storage.googleapis.com/2.10/chromedriver_linux64.zip`
 * `unzip  chromedriver_linux64.zip`

* Make sure chrome is install at **/usr/bin/google-chrome**

* `python selenium_scraper.py`

* Snippet (with various browser choices, remove the comment of the one you want to use and comment out the other ones):

`# use firefox to get page with javascript generated content
  #with closing(Firefox()) as browser:
  #with closing(Chrome()) as browser:  # PhantomJS
  #with closing(webdriver.Remote("http://localhost:9515", desired_capabilities=DesiredCapabilities.CHROME)) as browser:  # Fake chrome.
  # Don't know why it's not working with relative path. Pass absolute!
  with closing(webdriver.Chrome('/home/haku/chromedriver')) as browser:  # Fake chrome.
    browser.get(url)
    WebDriverWait(browser, timeout=30).until(
        EC.presence_of_element_located((By.NAME, element_name_to_check)))
    page_source = browser.page_source`

* Full Code (including a small web.py server in order to parse regexp from a site which has ajax loaded content):
https://github.com/hakanu/selenium_scraper

## Appendix:
* http://stackoverflow.com/questions/19015870/using-with-python-selenium-webdriverwait-in-pysaunter-for-async-pages
* http://selenium-python.readthedocs.org/en/latest/waits.html
* http://stackoverflow.com/questions/7593611/selenium-testing-without-browser
* http://selenium-python.readthedocs.org/en/latest/locating-elements.html
* https://code.google.com/p/selenium/wiki/ChromeDriver
* https://code.google.com/p/selenium/wiki/PythonBindings
* http://selenium-python.readthedocs.org/en/latest/getting-started.html
* http://stackoverflow.com/questions/22558077/unknown-error-chrome-failed-to-start-exited-abnormally-driver-info-chromedri
* http://stackoverflow.com/questions/22424737/message-uunknown-error-chrome-failed-to-start-exited-abnormally


#### Raspberry Pi
Raspberry pi does not have firefox package instead there is this iceweasel and gnash plugin for flash:
`sudo apt-get install iceweasel browser-plugin-gnash`

In order to install chrome on Raspberry pi for normal usage:
`sudo apt-get install chromium-browser`

However, these methods didn't make my scraper go through the page that I want to parse because of the lack of the flash support.