---
layout: post
title: Adding comments, analytics, and verifying the site
date: 2024-07-16 14:02 -0500
categories: [Website, Updates]
tags: [website_development]     # TAG names should always be lowercase
---

---
After initially setting up this site, and making the first post, there were still a couple of changes needed to be made in order to make the site more functional. This includes various analytics, verifications, and adding functinonal comments!

## Linking to Google Analytics
The first thing up was to connect to [Google Analytics](https://marketingplatform.google.com/about/analytics/). This way I can track the viewers of the site, see which posts they visit, and see when and where they link off the site. Linking to Google Analytics is fairly easily, especially when using [Chirpy](https://chirpy.cotes.page/) with [Jekyll](https://jekyllrb.com/).

The first step was to login to Google and create a data key. All I needed to do was link the url of my site and it was ready to go! Normally you would need to insert a snippet of HTML provided by Google, but using Chirpy, all I needed to do was insert my ID into the config file. I looked at the source code to find it, and there it was! I verified that it was working in my analytics dashboard, and now I could see all the analytics data! All 1 users!

![Google_Analytics_Screenshot](assets/posts/2024-07-16-adding-comments-analytics-and-verifying-the-site/Google_Analytics_Screenshot.png)

## Verifying Google Webmaster
Another item on the list of configurations needed, was to verify with Google Webmaster. Veryifying with your site with Google, allows you to see how they are categorizing you sites, which can help with optimization and SEO. 

There are a couple of ways to verify with Google, but once again, Chirpy allows for an easy automatic verificaiton for your site. All you have to do it to connect your ID. So, several minutes of trying to find which ID number (of which there are many) Chirpy needed, and pushing the site, Google was able to verify it. Now Google knows I own it, and gives me metrics about how it is categorized in their search.

![Verified_Site_Screenshot](assets/posts/2024-07-16-adding-comments-analytics-and-verifying-the-site/Verified_Site_Screenshot.png){: w="400" h="800"}

## Adding comments using Giscus
The final thing I did was adding comments to the site. Normally, adding comments takes quite a bit of work. The comments typically need to be stored on some server somewhere, which can take a lot of work to set up. On top of that, you would likely have to pay for the server, which could get quite expensive. Luckily, there are a few way comments can be set up using [Github](https://github.com).

One of the ways to do this is by using a Github app called [Giscus](https://giscus.app). With Giscus, you can create a GitHub repository that stores comments for you. Giscus in particular stores them on the discussion threads of Github. The user will verify their comment thorugh GitHub and it automatically copies over your picture and username! The documentation for Giscus is a bit lacking, so I looked towards another post where a user named [Yury Zhauniarovich](https://zhauniarovich.com/post/2021/2021-06-giscus/) detailed how he implented it for his site.

So I created a new public repository and enabled discussion threads on it. Next I installed Giscus through GitHub apps, and linked it to the repo. In order to find the desired settings, I looked at the Giscus set up and copied the setting into my config file. I pushed the site, and now the comments are up and running!

![First_Comment_Screenshot](assets/posts/2024-07-16-adding-comments-analytics-and-verifying-the-site/First Comment Screenshot.png)

## Conclusion
And that't it! More changes and features added to the site! Turning it from a mostly normal and boring site, to a normal and boring site that can track you with analytics!