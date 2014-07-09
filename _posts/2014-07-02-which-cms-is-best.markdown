---
layout: post
title:  "Which CMS is best? It's complicated."
date:   2014-07-02 21:11:00
categories: web-ed CMS
---

As I've said in a previous post about content management systems, we can tussle over which is best until we turn purple.

I've worked with quite a few by now, and here's a quick rundown on some of them, and why I like them. I'll try to revisit this post from time-to-time as things evolve.

## [Drupal][drupal]
Drupal remains my favorite CMS, hands down. It hasn't historically been the most pleasant to work with at all times, but it's steadily improving, and my early experience with Drupal 8 has been awesome.

A lower-level tool than many systems, Drupal straddles the line between CMS and pure PHP framework. It's extremely developer friendly, and you can build anything from a standard site to a Twitter clone using Drupal and some custom code.

Throw in an awesome community with very active IRC channels, a slew of modules that are completely free to install and a security team constantly identifying issues in contrib – Drupal takes the cake, in my book.

## [WordPress][wp]
WordPress – Not a distant second by any means, WordPress sports a fantastic community, a wealth of free, open source plugins and  the prettiest admin interface in the game. If your WordPress site is built by someone who knows what they're doing, adding content will always be a great experience.

As a developer, WP is the easiest CMS to build with, but I find its blog-first roots to be a bit odd when coming back from other systems sometimes. In short, WP has its way of coding, Drupal has its own, and I find Drupal's approach to be the most flexible and enjoyable to code for.

When I do a new WordPress theme from scratch, I like to start with Roots. It brings a lot of awesome to the table and helps me feel a bit more at home.

If you just need a basic website with a blog, you can't go wrong with WP. If your site's going to be larger, need serious custom functionality (customer portals, paywall content and the like) at some point, WordPress may not be the ideal choice.

WordPress also gets bonus points as the one I personally recommend for people interested in learning how to code. As a webdev, it's where I truly got my start.

## [Jekyll][jekyll]
Jekyll isn't technically a CMS, but it helps me manage and publish content, so I'll call it one anyway. It's a static site generator. You build templates, create Markdown files containing your content and generate your site.

You can't use it to handle form submissions. You can't have users logging in. You've got to be a bit geeky to work with it, and you'd have to mix it with other solutions to get any server-side interactivity.

Why use Jekyll, then? Glad you asked. Speed. Speed is the answer. Jekyll is ridiculously fast because the server isn't running any app code to serve pages. They're all already there, as though you made each one individually in Dreamweaver or something. This is pretty much what Web servers were originally designed to do, and they do it well.

[Studies have shown][pageloads] that the longer your site takes to load, the greater the chance that you will not convert that user, whether your CTA is to buy something or subscribe to a newsletter. People like fast sh*t.

Also, this is as easy to design for as a platform can be. You can create a base HTML file that looks exactly how you want your website to look and Jekyllize it very quickly.

This site is built with Jekyll. Combine that with SSD hosting at DigitalOcean and things are pretty damn snappy, no? As such, Jekyll's my new recommendation for any situation where it can possibly fit, even for cases where it needs to be shoehorned just a little.

For bonus reading, see how [Obama's campaign website][bama] leveraged Jekyll to increase conversions.

## [concrete5][concrete5]
Concrete5 is another one I've seen gain more traction recently, so I'd taken it for a spin. I'd describe it as a balance between Jekyll and other systems. It was among the first I'm aware of to feature in-context editing, which is especially cool when building a site for people who consider themselves especially computer illiterate.

The thing that makes it Jekylly is the speed with which you can go from design to website. It's another pretty easy templating system, at least for getting a basic setup going. Definitely worth taking for a spin.

It's the add-ons that turn me off. Even glancing at its marketplace of add-ons now, I'm seeing open source software repackaged for concrete and being sold for $50. I'm not wiring it up to try, so there may be serious added value that's worth the money, but this is a far cry from what I'm accustomed to.

## [Joomla!][joomla]
Joomla! is another big one. I'll admit, it's been a long while since I've worked with it. It's always felt a little dirty to me. Drupal's documentation is great, save for the occasional unfinished page. The WordPress documentation has always been legendary. Joomla!'s has always been fragmented and underwhelming when I've looked for it. That's bad.

One bonus I gather from Joomla! is it's supposed to be pretty flexible, but I've never tried using it that way, and can't speak to its APIs and such.

I'd love to have a conversation with a Joomla! expert who could explain what he sees in it, but as it stands I can't recommend Joomla! over Drupal or WordPress. That may be entirely because of my lack of experience with the CMS, so don't take my word for it.

## [Microsoft Sharepoint][shit]
Just typing Sharepoint makes me want to puke. I haven't had to do much with it, but what I did have to do was a bad experience.  It's always seemed like a confused product, but it looks like it's improved a bit.

I'm not a Microsoft dev these days, so if you are, Sharepoint may be awesome for you. It may be the best option if you're building for a company that's already deep into Microsoft products and you need to integrate. But this is definitely not the platform you'd choose for a blog...
 

[drupal]: https://www.drupal.org/ "Learn more about Drupal"
[wp]: http://wordpress.org/ "Learn more about WordPress"
[jekyll]: http://jekyllrb.com/ "Learn more about Jekyll"
[pageloads]: http://blog.kissmetrics.com/loading-time/ "An article on how page load times can affect your conversions"
[bama]: http://kylerush.net/blog/meet-the-obama-campaigns-250-million-fundraising-platform "A blog detailing a serious, real-world Jekyll deployment"
[concrete5]: http://www.concrete5.org/ "Learn more about concrete5"
[joomla]: http://www.joomla.org/ "Learn more about Joomla!"
[shit]: http://office.microsoft.com/en-us/sharepoint/ "Learn more about Sharepoint"