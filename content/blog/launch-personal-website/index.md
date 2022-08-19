---
author: Wenjia Zhu
categories:
- Personal Website
- Life
date: "2022-08-16"
draft: false
excerpt: This blog demonstrates how to launch your personal website from scratch. I'll walk you through step-by-step beginning from registering GitHub and configuring hugo template to finally deploying through Netlify.
layout: single-sidebar
subtitle: Building your website using R {blogdown}
tags:
- hugo-site
- R blogdown
title: Launch your personal website in 1 hour
---

I've always wanted to build a personal website to show the world what I'm capable of, but was scared off by a variety of skills required, such as html, CSS and Javascript. To get myself better prepared, I attended a very good udemy course named "The Web Developer Bootcamp" by [Colt Steele](https://www.udemy.com/course/the-web-developer-bootcamp/), where I was able to understand some basic skills used for both frontend and backend web development. 

But still, developing a personal website could ask for hundreds of hours if you want to start from scratch. Another option to consider is customizing from some open-source theme templates, thanks to these talented web developers out there! So before I started building my personal website, I decided to do some research first. Luckily, I came across a very beautiful [hugo theme](https://hugo-apero-docs.netlify.app/) (developed by [Alison Hill](https://www.apreshill.com/about/)) that not only fits my aesthetics, but also contains all the web sites I wanted to include in my personal website. The only drawback to me is that the theme is supported by blogdown R package, which I've never tried before. So this could be challenging at the first place. However, if you're like me, don't get run away - you're just 1-hour away from owning a personal website! Let's get it started!🚀

---

## 1. Set up

To start with, you'll need to install the following:

<i class="fas fa-download pr-1 fa-fw"></i> Install recent versions of R and Rstudio

<i class="fab fa-github pr-1 fa-fw"></i> Create a GiHub account

<i class="fab fa-r-project pr-1 fa-fw"></i> Connect to GitHub from RStudio
+ Create a new GitHub repository for your website project
+ Navigate to https://github.com/your-username/your-repository
+ Click on the green "Code" button
+ Copy the HTTPS link to your clipboard
+ Go to `RStudio > File > New Project > Version Control > Git`
+ Paste HTTPS link under Repository URL
+ Select "Create Project" to complete

<i class="fas fa-user-plus pr-1 fa-fw"></i> Sign up Netlify using your existing GitHub account 

Next, we'll use the blogdown package to make a Hugo website from the comfort of RStudio. If you don't have one, run the following command line:
```
install.packages("blogdown")
```
We'll then use Hugo to build the site, so we use the blogdown package to install Hugo:
```
blogdown::install_hugo()
```

## 2. Create website

In the console of RStudio, we'll create a new site with the Hugo Apéro theme:
```
library(blogdown)
new_site(theme = "hugo-apero/hugo-apero", 
         format = "toml",
         sample = FALSE,
         empty_dirs = TRUE)
```
Please take a minute to read the printout in your console, as you will be asked if you want blogdown to start a local server for you. Select y so you can have a local version in the RStudio Viewer pane.

*Tips: If you ever want to start or stop the local server, you can type the following command in the console:*
```
blogdown::serve_site()
blogdown::stop_site()
```

# 3. Deploy your site

We'll first push your site to Github <i class="fab fa-github pr-1 fa-fw"></i>, and then connect Netlify to GitHub repo. Netlify will continuously detect the push, re-build, and launch your wesite automatically. I have been amazed at how quickly my site rebuilds through Netlify right after I commit my changes and push to GiHub! 🤩

## Push to GitHub
Since you've cloned that GitHub repository into your  RStudio project, you can use the "Git" tab in the upper right pane to commit:
+ Click the "Git" tab in upper right pane of RStudio
+ Click on "Diff" for a pop-up window, and check the changes you've made for files
+ Type a message in "Commit message" textarea
+ Click "Commit"

*Tips: I found a very good reference for [Version Control with Git from RStudio](http://rstudio-pubs-static.s3.amazonaws.com/272737_7d6178a0e50043528d9ba636fdde209e.html). 
Also, if you failed cloning, it is likely due to the retirement of using username/password by GitHub. Instead, you'll need to generate a Personal Acccess Token (PAT) from the GitHub website, and try performing git push operations over HTTPS. You can find how to generate PAT and push from this great [article](https://techglimpse.com/git-push-github-token-based-passwordless/) with detailed explanation and screenshots step-by-step.*

### Connect Netlify
After you log in your Netlify account and select: `New site from Git > Continuous Deployment: GitHub`, please choose the repo you've been working with and select Deploy Site.

The Netlify will then provide you with the link to your new site! Since Netlify supplies so-called "continuous deployment"", it will track any changes you commit and push to GitHub and update your published site accordingly.

**At this point, you've successfully launched your website! Cheers!** 🍻 

The next step is to rename your site, as Netlify just assign you a random subdomain name. You can go to Settings, and click on "Change site name" under Site information. You'll then update your baseURL in your site configuration file (`config.toml`) to match the link where Netlify is publishing your site.
```
baseURL = "https://hugo-apero-docs.netlify.app/"
```

#### If you follow all the steps above, you've already deployed a personal website! Click the url link and see it alive!

![Congratulation](Congratulations-clip-art-free.png)

---

I will stop here to make this blog concise and more reader-friendly. Hope you enjoy reading so far! This is just the start of your journey to create a website belongs to **YOU**. Don't stop here, and keep tailoring the site for your specific needs! 🎉



