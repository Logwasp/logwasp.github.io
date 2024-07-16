---
layout: post
title: "Creating my Personal Website"
date: 2024-07-15 19:36 -0500
categories: [Website, Creation]
tags: [website_development]     # TAG names should always be lowercase
description: The initial development of this website your looking at right now, and its first post!
---

---
In hopes to expand my personal portfolio and coding skills, I decided to create this personal website to document my personal projects! This post will give a general outline of how I created the very basics for this website.

## Setting up the site
### Templating with Jekyll and Chirpy
For this project, I decided I was going to use [Jekyll](https://jekyllrb.com/), a static site generator. One of the many reasons that makes Jekyll particularly popular is its templating community. With many templates to choose from, and the ability to switch between templates, it makes scripting blogs like this much faster than in standard HTML.

My website uses [Chirpy](https://chirpy.cotes.page/), a popular and feature rich template for Jekyll.

To begin, I started by forking the Chirpy repository to to my GitHub. You can view the code [here](https://github.com/Logwasp/logwasp.github.io). After forking and downloading, I ran the neccesary commands to bundle and initialize the site, and them ran it for the first time!

![Initial_Personal_Website_Screenshot](assets/posts/2024-07-15creating-my-personal-website/Initial_Personal_Website_Screenshot.png)
_A picture of the website after initial setup_

### Publishing with GitHub Pages
But what fun is a website if only you can view it? So now it's time to get it up and running! The easiest way to do this is to run it with GitHub pages. This way, I could store and run it for free, using tools I was already familiar with. However, since Jekyll is compiled, it required a little extra set up. So, I set the page to recompile every time I pushed a commit to the repository. This way, I dont have to manually build it every time I want it to run! Now the site was running at [logwasp.github.io](https://logwasp.github.io)

## Personalizing the site
### Adding avatar and fixing socials


So now the site is up and running, but it was looking a little.... boring. To fix this I first added my profile avatar.  Afterall, my face is not a plain grey circle.  Then, I added my a name and description, as well as customizing which social sites the sidebar shows and links to.

![Desktop View](assets/posts/2024-07-15creating-my-personal-website/Customized_Avatar_Screenshot.png){: w="200" h="800"}

### Adding about me

I customized the [about me](/about-me), adding a little bit of information about me and more importantly, a picture of the objectively best dog in the world. This provided the first real oppurtunity for me to use Markdown, a simple language used to make writing HTML blog posts faster. The About Me page was written in Markdown, as well as this post!

![About_Me_Screenshot](assets/posts/2024-07-15creating-my-personal-website/About_Me_Screenshot.png)
_A screenshot of the About Me page_

### Writing the first post
Finally, it was time to write the first post, this post! In order to make writing them easier, I download a ruby gem, [Jekyll-Compose](https://github.com/jekyll/jekyll-compose) to generate templates for the posts. After generating the post, I added a few tags to make it easier to categorize and sort the posts. After the post was generated and initialized, it was time to start writing. Like the About Me page, the posts are written in Markdown.

![First_Post_Markdown_Screenshot](assets/posts/2024-07-15creating-my-personal-website/First_Post_Markdown_Screenshot.png)
_A screenshot of Markdown written for this post_

### Conslusion
And that's it. The site is up and running, and the you're reading its very first post! Who knows what is next for it! In the future, I'm hoping to add Google analytics to the site, and potentially customize it to add some more color. But those are for a future post!
