---
layout: post
title: Hello World!
tags: site-foundation
---

I always wanted to create a personal website. But I was too lazy or too preoccupied with many things in life. But because of [COVID-19](https://www.who.int/emergencies/diseases/novel-coronavirus-2019),  I found myself having an extra time and motivation to finally make it happen.

Basically, I was looking for the following criteria to host this site.
* Relatively secure
* Less site maintenance
* Affordable

#### Relatively secure

Based from [some website hacking statistics](https://www.webarxsecurity.com/website-hacking-statistics-2018-february/), a lot of websites get hacked every day. I was afraid I will use more time defending the site than creating contents. In my opinion nothing is unhackable, but I was aiming to at least limit the risks of being hacked. 

#### Less site maintenance

There are many ways to host a personal website, but first I had to choose between self-hosting or hosted service. For self-hosting I have the option of using a Raspberry Pi, an existing router, or a NAS since I already have those devices. But I just want to focus on the content. I don't want to spend my time maintaining the server (both hardware and software). Using a respected web hosting service would also remove the responsibility of securing the site from hands.

#### Affordable

Many blog web hosting services exist. [Wordpress](https://wordpress.org) and [Github Pages](https://pages.github.com) are very popular, and they both offer free tier which is more than enough for my case. 



### Github Pages for hosting

Wordpress has a bad reputation when it comes to security. I also thought it was an overkill for my use case so I decided to use Github. In addition to publishing personal websites, Github offers resource management  (website’s source codes and contents) using a git repository. It means all changes to the website will be backed up and can be tracked in a very efficient way.

The problem with hosting services, including Github Pages,  is that your website address (URL) is not really personal. For example, when you publish a website using Github Pages, your URL will be `username.github.io`. If you like to have `my-own-web-address.com` you need to register a domain name (of course it needs to be available as well). 

### Namecheap for domain name registration

I tried [Namecheap](https://namecheap.pxf.io/VPgA3), [Google Domains](https://domains.google), and [Domain.com](https://www.domain.com) to register my choice of the domain name. Namecheap live up to their name and offered the cheapest, Google Domains was 35% more, and Domain.com would be more than double of Namecheap. Removing privacy protection from Domain.com will slash almost half of the price, but that protection is included with the cheaper Namecheap and Google Domains.

### Look and feel of this site made possible by Jekyll and Hyde

I’m using [Jekyll](https://jekyllrb.com) as a static site generator since Github Pages supports it by default, and for the mean time I’m using [Hyde](https://hyde.getpoole.com) as the theme.


### Conclusion

Using a static site generator for a website hosted on Github Pages allowed me to accomplish my goal to start a personal website according to my criteria. It’s relatively secure, no server maintenance, and cheap (I only pay for the domain name, while hosting is free).