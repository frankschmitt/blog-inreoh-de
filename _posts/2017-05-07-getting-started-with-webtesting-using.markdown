---
layout: post
title: Getting started with WebTesting using Selenium / Geb + Kotlin
date: '2017-05-07T06:46:00.000-07:00'
author: Frank Schmitt
tags: 
modified_time: '2017-05-07T06:46:53.328-07:00'
blogger_id: tag:blogger.com,1999:blog-6373343020354235841.post-319931685803493186
blogger_orig_url: http://inreoh.blogspot.com/2017/05/getting-started-with-webtesting-using.html
---

# Installation  
## Remove broken firefox binaries 
If you encounter a 
  "Could not find the Mozilla runtime."  
error when Firefox is started, ensure you don't have broken firefox binaries lying around; in my case:    
 ```sudo mv /usr/local/bin/firefox /usr/local/bin/firefox.bak
 ```
 
 ## Modify your path to include the firefox binary 
 PATH=/Applications/Web/Firefox.app/Contents/MacOS/:$PATH   
 
 ## Install necessary components 
 ```
 brew install selenium-webdriver-standalone geckodriver chromedriver 
 ```
