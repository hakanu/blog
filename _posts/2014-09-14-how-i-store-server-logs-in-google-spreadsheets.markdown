---
layout: post
title: How I store server logs in Google Spreadsheets
date: '2014-09-14 22:45:58'
---

![](http://scontent-b-ams.cdninstagram.com/hphotos-xpa1/t51.2885-15/1208362_537671056315500_779010380_n.jpg)

**Disclaimer:** I'm not an expert in this field. I just want to share my experiences with logs, you are welcome to give some feedback on my method.

I like logs, I hate logs. I like analyzing them but I don't like dealing with backups and everything.

I have small sized projects like [isimibul](https://play.google.com/store/apps/details?id=co.hakanu.jobfinder) (job search engine for Turkey), [Football Video Highlights](https://play.google.com/store/apps/details?id=haku.io.wc_goals). They have 3k-4k page views (API hits) per day. I would like to analyze some usage statistics like how many msecs it takes to handle a request or which job term is searched the most.

At first I was using txt files to keep the logs. After some point it became real pain and I need some structured data. I started to log into sqlite in the server machine. However, that small sqlite file started to become something giant. As far as I observed (I might be wrong), dealing with big sqlite files increased the RAM usage of the server. So periodically I needed to back up and clean the logs (rm -rf is our friend). This system pushed me to find something more streamlined. I saw people who log to json files, I was about to use logstash which looks awesome (I don't want to set up another server for logging). I stumbled upon blazedb which is like nosql sqlite:P Before starting to use it, I saw a repo in github which occupies Google Drive's **spreadsheets** as database which is butterdb described below. I quickly played with it. It was ok for a fun project. However it was missing a couple features like batch inserting for my needs.

According to the spreadsheet data storing method, Each spreadsheet is like a database, each worksheet is like a table, columns are like a relational db columns and rows are like records.

![](https://devdala.files.wordpress.com/2014/08/screen-shot-2014-08-29-at-15-29-131.png)

Butterdb did not have batch insert so I wrote my very own small wrapper (Inspired by [butterdb](https://github.com/Widdershin/butterdb) and used [Gspread library for python](https://github.com/burnash/gspread)) which is mostly focused on inserting data into spreadsheets, of course you can fetch data from it using regular experessions:
https://gist.github.com/hakanu/be6098447e4d74d26eca

For developers:
[Gspread API reference](http://burnash.github.io/gspread/)

## Advantages
* Reliable, robust storage in the cloud
* Large quota allowance, see below for more.
* No need to set up crons to fetch the logs from server computer and back up
* Builtin version control
* Easy access control, just give access to some mail addresses from Google Drive UI
* No need to create a log UI
* Builtin **formulas** to be able to process the data, be able to do fantastic analysis on data like MS Excel
* Batch inserting
* One click CSV (and other formats) export
* Rich data representation pallet
* Automatically run the formulas when data is updated
* Builtin **charts** and graphs.
* Access your data and its summary and graphs from any device you have including iOS ones.(Well, graphs are not rendered on phones)
* Gspread has cool data fetching methods like using regexp
* **Nosql**-ish inserts. Sheets don't really care how many columns you insert or what type you used. Not having the type safety might be an issue from some aspects.

## Disadvantages
* Using a tool on something which is not meant to do that job - who cares we are hackers. After I saw that a guy used [git as a nosql database](https://speakerdeck.com/bkeepers/git-the-nosql-database), I think sky is the limit
* Connection is needed to be kept alive, one extra thread to refresh connection periodically
* Not as fast as a database, this may be the biggest showstopper. See the stats below.
* No db modelling, at least in my code. Butterdb provides this. Can be an advantage for some people.

## Restrictions of Google Spreadsheets

* As of 2014-09-14, according to [google's official page](https://support.google.com/docs/answer/37603?hl=en):

>Spreadsheets: 400,000 cells, with a maximum of 256 columns per sheet. Uploaded spreadsheet files that are converted to the Google spreadsheets format can’t be larger than 100 MB, and need to be under 400,000 cells and 256 columns per sheet.

## How about the speed?

Tests are done on Intel Core i7 3635QM 2.40GHz with ~100mbit download, ~10mbit upload (with 8ms ping) network on Ubuntu 14.04, python2.7, SSD powered.
[timeit](https://docs.python.org/2/library/timeit.html) is used for measuring clocks.

PS: I know that **sqlite** is incomparable to the GS, it is not a fair fight (sqlite is based on local file, GS hops over network by passes several auth processes). One more thing, for the batch insert, there is a workaround in my wrapper which is that it inserts empty cells first and after that updates them. This causes 2-step insertion. However I put it here just for some performance flavour. I will try with postgres when I have time. For now, here are the stats.

<table>
  <tr>
    <th>nRows</th><th>nCols</th><th>Single insert?</th><th>Comp (ms)</th><th>Comp sqlite (ms)</th><th>Col size (byte)</th>
  </tr>

  <tr>
    <td>1</td>
    <td>25</td>
    <td>Y</td>
    <td>5367.38</td>
    <td>14.88</td>
    <td>6</td>
  </tr>
  
  <tr>
    <td>1</td>
    <td>5</td>
    <td>Y</td>
    <td>1651.46</td>
    <td>15.77</td>
    <td>6</td>
  </tr>
  
  <tr>
    <td>1</td>
    <td>1</td>
    <td>Y</td>
    <td>882.73</td>
    <td>15.38</td>
    <td>6</td>
  </tr>
  
  <tr>
    <td>100</td>
    <td>25</td>
    <td>N</td>
    <td>6145.69</td>
    <td>355.44</td>
    <td>6</td>
  </tr>
  
  <tr>
    <td>100</td>
    <td>5</td>
    <td>N</td>
    <td>5520.64</td>
    <td>323.50</td>
    <td>6</td>
  </tr>
  
  <tr>
    <td>100</td>
    <td>1</td>
    <td>N</td>
    <td>5424.45</td>
    <td>355.07</td>
    <td>6</td>
  </tr>
</table>

## Conclusion
There are plenty of rooms to be developed in the wrapper for sure. But for now I'm pretty happy with my current setup. I will migrate my other applications' logs when I have time.
I use a synchronized queue for temporarily holding logs in the memory until they are persisted by a thread.