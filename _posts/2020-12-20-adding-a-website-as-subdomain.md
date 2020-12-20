---
layout: post
title: Adding a Website as Subdomain
description: How we add a new website as subdomain...for free ofcourse
tags: site-foundation
---

One day my son suddenly decided he wanted the stories he's been passionately making to be uploaded to a website. We did not want to spend anything on this adventure and he wants to see it live as soon as possible. Very demanding boy.

## Creating a fresh new website on a tight schedule

Since he already has the contents locally in [markdown](https://en.wikipedia.org/wiki/Markdown) format, we decided to just create a copy of this site and replace the contents with his own. Moreover, there is no need for a new domain so we created a subdomain on himbak.com. It did not cost us anything other than our time which did not take that much either.

### Creating the website

1. Create a new GitHub account and fork himbak.com's [source](https://github.com/roweldelrosario/roweldelrosario.github.io).
2. [Change](https://github.com/rj1delrosario/monogatari/commit/b44e7166430e448b82d12f484fdfb7f7d6fc51ad) a few settings and replace the existing posts with his own.
3. Host the new website on Netlify.

himbak.com is being hosted on Netlify and all we did was to [add a new site from git](https://www.netlify.com/blog/2016/09/29/a-step-by-step-guide-deploying-on-netlify/). After the new site was built and published, it became live at [infallible-kare-6e9e2b.netlify.app](https://infallible-kare-6e9e2b.netlify.app) and we can stop[^1] here if we do not need a nicer [^2] website address.

[^1]: url settings on _config.yml need to be fixed
[^2]: You can change the site name but it will still bear the *netlify.app* domain.

### Creating the subdomain

I told him to think of a name for his website and we settled for *monogatari* (物語), which means *story* in English. Eventually, *monogatari* will become a subdomain of *himbak.com* resulting in ```monogatari.himbak.com``` as the final address.

What we wanted to do is to show the contents of the website hosted on Netlify (*infallible-kare-6e9e2b.netlify.app*) when someone goes to *monogatari.himbak.com*.

I used [Namecheap](https://namecheap.pxf.io/VPgA3) to register himbak.com but I'm using Cloudflare as [Nameserver](https://en.wikipedia.org/wiki/Name_server). So we need to tell Cloudflare that the name *monogatari.himbak.com* points to *infallible-kare-6e9e2b.netlify.app*.

1. Log in to Cloudflare and go to the DNS management menu for the existing site.
2. Add a new DNS record.
	- Select CNAME for the *Type*
	- Input the desired subdomain for the *Name*
	- Input the target website address for the *IPv4 Address*

Here are the settings in our case.
```
Type: CNAME
Name: monogatari
IPv4 Address: infallible-kare-6e9e2b.netlify.app
TTL: Auto
Proxy Status: DNS Only
```

[https://monogatari.himbak.com](https://monogatari.himbak.com) is now live and my son seems happy about it.



