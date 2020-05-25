---
title: "Web Scraping and APIs"
date: 2020-01-30
tags: [BeautifulSoup]
header:
  image: "/images/dog-breed/banner.png"
excerpt: "Bs4"
mathjax: "true"
---

## Overview

These python scripts request and `get` data from various websites. In these cases, weather and HackerNews. Note - check what is allowed to be scraped by appending "robots.txt" to the end of a website (i.e. https://www.airbnb.ca/robots.txt provides a full list for airbnb's policies). APIs are a great way to obtain website info where assuming user access (API TOKEN) website information can be sent in a convenient JSON form.

HackerNews like many active websites gets updated frequently where sifting through pages of posts becomes cumbersome. I created a python script that scrapes the website and only returns those posts relevant. In my case, stories with a score > 99 and returning a descending list. This way I can read a short list of posts most relevant without searching and clicking through irrelevant posts.

The script can also be applied to discovering trends and returning only information needed. BeautifulSoup is a popular Python library to web scrape. With BeautifulSoup, it's easy to scrape for selected data such as HTML anchors, </div> tags, etc. Note, also need Requests library to request data from website.

TO INSTALL BeautifulSoup and Requests:

> pip3 install beautifulsoup4
> pip3 install requests

TO RUN in Python script

“`Python

import requests
from bs4 import BeautifulSoup
import pprint

response = requests.get('https://news.ycombinator.com/news')
response2 = requests.get('https://news.ycombinator.com/news?p=2')

# print(response.text)

soup = BeautifulSoup(response.text, 'html.parser')
soup2 = BeautifulSoup(response2.text, 'html.parser')

“`
