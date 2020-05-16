---
layout: post
title: Steps to create this website
description: My experience to create a personal website in 2020. 
tags: site-foundation
---

Following are the steps I took to make this site online.

### 1. Prepare a Github Pages site

Just follow what is written on [Github Pages](https://pages.github.com). You need a [Github](https://github.com) account to proceed, so sign up for a free account if you don’t have one.

[Jekyll](https://jekyllrb.com) has a default theme, but you can use a different one you like. I forked the [Hyde theme repository](https://github.com/poole/hyde) and add a few changes related to tagging which comes from [another repository](https://github.com/qian256/qian256.github.io), which is also based on Hyde theme.

I’m using a Mac to test the site locally. You can follow the steps from [Github Help](https://help.github.com/en/github/working-with-github-pages/testing-your-github-pages-site-locally-with-jekyll). I already have Ruby, so I just installed Jekyll and clone my Github repository to a local directory.

After local changes are pushed to your Github repository, you can check the published version at `username.github.io` where `username` is your Github user account.

### 2. Register a domain name

Go to [Namecheap](https://namecheap.pxf.io/VPgA3) and check if your desired domain name is available.

You don’t have to type `.com` and you are not required to use `.com` if you don’t want to. If the domain is already taken, you can use a different domain name extension (like using `.io` instead `.com`), or search for an entirely different name.

The search results will show many suggestions, as well as how much it would cost. After you have decided which one to go for, add to cart then proceed to checkout.

### 3. Use your domain name for your Github Pages site

You need to make a connection between the domain name you registered at step 2, and the Github Pages site you created in step 1.

In my case, when someone uses a web browser and input [himbak.com](https://himbak.com)(my domain name) in the address, I want the browser to show the contents of [roweldelrosario.github.io](https://roweldelrosario.github.io/)(my Github Pages site).

You can follow the steps laid out at [Github Help](https://help.github.com/articles/setting-up-a-custom-domain-with-pages). For the part in Github Help where you need to create a CNAME record on your DNS provider, the specific instruction for Namecheap can be found in [this knowledgebase link](https://www.namecheap.com/support/knowledgebase/article.aspx/9645/2208/how-do-i-link-my-domain-to-github-pages).

### That's it

Steps 1 and 2 are independent of each other, so you can do step 2 first before step 1. But you need to finish both step 1 and step 2 before proceeding to step3. Also, please note that you don’t need step 2 and step 3 if you are happy with having `github.io` in your website address.

You might also want to check the [Enforce HTTPS](https://help.github.com/en/github/working-with-github-pages/securing-your-github-pages-site-with-https) setting for your Github Pages site, unless you want web browsers to flag your site as *Not Secure*.

---

**Updated Monday April 27, 2020**

Currently, this site is no longer directly hosted by Github Pages. From [this post](https://himbak.com/2020/04/19/site-security/) I described how I made a few changes related to site security, changing the way how the site is deployed. The raw resources for building the site are still on Github, but the site is now served through Netlify. 

The [Github repository](https://github.com/roweldelrosario/roweldelrosario.github.io) now has two branches: *master* and *himbak*. Changes related to the site theme will be on *master* branch, while *himbak* branch contains the posts. My [GitHub Pages](https://roweldelrosario.github.io/) site, which is connected to *master* branch, will show the theme along with some sample posts. On the other hand, Netlify automatically builds [himbak.com](https://himbak.com) from *himbak* branch. By having two branches like this, I can experiment on the user interface (using the *master* branch)  while not affecting the main site (which is using the *himbak* branch). Eventually, my workflow will involve just adding posts to *himbak* branch.
