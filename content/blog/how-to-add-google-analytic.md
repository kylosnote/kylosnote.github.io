---
title: "How To Add Google Analytic (GA4) To your website"
date: 2023-07-21
type: "blog"
tags: ["blog", "ga4", "google analytic"]
keywords: ["ga4", "google analytic", "how to"]
description: "A simple guide to add Google Analytic (GA4) to your website."
summary: "After migrating from Jekyll to Hugo, my GA tag was gone. So I have to add it back."
---

In order to add Google Analytic there is multiple options.
- Install manually using the script provided.
- Install using Google Tag Manager (GTM).
- Install with a website builder or CMS

For my case, I am install manually using the script provided.

First and foremost, go to **[Google Analytic](https://analytics.google.com/)** and go to Admin setting page.

Create an Account > Property > Data Streams > Add Stream > Web

Upon created a Web Stream. You should get something like this.
![Google Analytic Web Stream](/img/1.JPG "Google Analytic Web Stream")

Please note that, you would not be seing the "Data collection is active in the past 48 hours." at this moment.

After that go to Configure tag settings > installation instructions > install manually

And you will have code similar to this.
```
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-JG1GFLMPVP"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-JG1GFLMPVP');
</script>
```

After that just follow the instruction "Copy and paste it in the code of every page of your website, immediately after the <head> element. Don’t add more than one Google tag to each page."

**How to know if you script running?**

After deployed that script, simply open your website and at the same time in Google Analytic Home Page check if there is any data.
![Google Analytic Data](/img/2.JPG "Google Analytic Data")

Voila! Its done.

For more resources:
    
[https://support.google.com/tagmanager/answer/12811173](https://support.google.com/tagmanager/answer/12811173)
