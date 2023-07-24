---
title: "Web scraping Jobs Ads Post To Discord With Bot"
date: 2023-07-24
type: "blog"
tags: ["blog"]
keywords: ["job hunt", "career", "python", "discord.py", "automation", "discord bot", "web scraping", "web scrape"]
description: "I Wrote a Python Discord Bot and web scrapping script to help me find job in New Zealand."
summary: "I Wrote a Python Discord Bot and web scrapping script to help me find job in New Zealand."
---

This year March I travelled to New Zealand under the Working Holiday Visa which allow me to work in New Zealand for six month. Not only that, the goverment of New Zealand decided to extend visa for another six month (See here)[https://www.frenz.co.nz/blog-post/working-holiday-visa-extension/] to know why. Which mean I can stay at New Zealand and work until March 2024

However, just because I can work here doesnt mean I can get a job easily. Especially when its the winter. So in order to make it easy for me. I wrote a web scraping script for some of the popular job adsverstiment website in New Zealand and use a Discord bot to run a scheduled task every one hour to do the web scraping.

The target website I used are [Seek](https://seek.co.nz), [TradeMe](https://trademe.co.nz) and [backpackerboard](https://www.backpackerboard.co.nz/).

The whole Discord bot and web scraping script are written using **Python** only.
Some of important python library I used include
- **discord.py**
- **aiohttp**
- **selenium**

Some website offer API endpoint and some doesn't. For those with API endpoint I can just use aiohttp to request the json data. As for those without API endpoint, I used Selenium + Chromedriver to scrape the whole page and get the data i want from element by element.

Here are the web scraping script screenshot.
![Code](/img/code_1.JPG "Code")

Some rules are applied in order to avoit getting too many job ads and spaming the Discord channel with it.
1. Only new job of the day will be collected
2. The job will based on location I set and send to the Discord channel coresponding to their location.
3. The script will run every one hour.
4. Previous message in the same day will be deleted so it easy to look back old job post.

Finally send to Discord as embed message.
Displaying the title, and location only for easy digest.
![Result](/img/pic_1.JPG "Result")

here are a list of location channel.
It is based on location I intended to visit so some region in New Zealand is not covered at the moment.
![Location](/img/pic_2.JPG "Location")

Some of the improvement can be made. For example, covering more website and avoid duplicate job post since some recruitor might post same job post on multiple website.