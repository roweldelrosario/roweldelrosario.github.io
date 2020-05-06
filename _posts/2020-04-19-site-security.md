---
layout: post
title: Site Security
image: public/image/security_report_after.png
tags: site-foundation
---

I have enabled the [Enforce HTTPS](https://help.github.com/en/github/working-with-github-pages/securing-your-github-pages-site-with-https) setting for my Github Pages site and confirmed that browsers are no longer labeling it as *Not Secure*. Good.

I was hoping that the site was already secure since browsers were no longer complaining. So I searched for a way to check the site security. I found [this okta blog](https://developer.okta.com/blog/2019/04/11/site-security-cloudflare-netlify) and checked my site using [securityheaders.com](https://securityheaders.com/). The result? Not good.

### Security Report Summary... Before and After

Below is a screenshot of the scan result from securityheaders.com before making any changes.

![Security Report Summary Before Changes](/public/image/security_report_before.png)

The *Site* from the report summary above shows my Github Pages site since I already fixed it before creating this post, but you get the idea. The IP Address shows one of the [A records for Github Pages](https://www.namecheap.com/support/knowledgebase/article.aspx/9645/2208/how-do-i-link-my-domain-to-github-pages).

I followed what is written in the okta blog to use [Netlify](https://www.netlify.com) to set HTTP response headers. Netlify  allows you to [publish a website using your Github repository](https://www.netlify.com/blog/2020/04/02/a-step-by-step-guide-jekyll-4.0-on-netlify/#connecting-to-netlify). They have a free Starter Plan that offers the same 100GB bandwidth limit as Github Pages, which is more than enough for this site.  So instead of directly hosting using Github Pages, your website will be served by Netlify's global CDN (Content Delivery Network).

I used the same Netlify configuration file as the one in the okta blog, but the `X-Content-Type-Options` header was still red. Searching from Google results to the need to add  `X-Content-Type-Options = "nosniff"` to the configuration. The following shows the contents of my [netlify.toml](https://github.com/roweldelrosario/roweldelrosario.github.io/blob/master/netlify.toml) file.

``` toml
[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    Content-Security-Policy = "form-action https:"
    Referrer-Policy = "strict-origin-when-cross-origin"
    X-Content-Type-Options = "nosniff"
    Strict-Transport-Security = "max-age=2592000"
    Feature-Policy = "vibrate 'none'; geolocation 'none'; midi 'none'; notifications 'none'; push 'none'; sync-xhr 'none'; microphone 'none'; camera 'none'; magnetometer 'none'; gyroscope 'none'; speaker 'none'; vibrate 'none'; fullscreen 'none'; payment 'none'"
```

After the site was deployed, I checked the security headers again and the result was A+ with all headers now showing as green.

![Security Report Summary After Changes](/public/image/security_report_after.png)

The result from [SSL Labs](https://www.ssllabs.com/ssltest/) also shows a green A (I was hoping for an A+ though).

![SSL Labs Result](/public/image/ssllabs_result.png)