```
title: Interactive Static Sites With Jekyll, Backbone.js, and Firebase
layout: post
tags: ['post']
date: 2013-05-03
author: Chris Smith (@quartzmo)
```


*Note: This post was adapted from a [slide presentation on quartzmo.com](http://www.quartzmo.com/presentations/backbone-firebase-jekyll/). That's why it's a bit heavy on bullet points.*

The term "interactive static site" appears to be an oxymoron. In fact, they are all over the Web and have been for years.
What's relatively new are developer-oriented site generation tools such as Jekyll; JavaScript MVC frameworks such as Backbone.js, Ember.js, and AngularJS; and Backend as a Service (BaaS) platforms such as Firebase and Parse.

## Why static sites?
Static web sites are extremely stable, secure, economical, and fast. They can be great for SEO and analytics, and work best when the *primary* content is infrequently changed and document-oriented.
This is true of most personal blogs, but also of many large sites, possibly even much e-commerce.
A [new version of healthcare.gov](http://developmentseed.org/blog/new-healthcare-gov-is-open-and-cms-free/) is slated to
be a massive static site, with content to be updated by non-technical users via [Prose](http://prose.io).

Indeed, the page you are reading was created and deployed with [Octopress](https://github.com/imathis/octopress), a blog-specific wrapper for the slightly more generic [Jekyll](https://github.com/mojombo/jekyll) project. Jekyll is complex software, based on Ruby, Rake, and Git. [Middleman](https://github.com/middleman/middleman) may be even more complex than Jekyll, and reminds me of a command-line version of Rails. These are the heavyweight, mature solutions. For learning the concepts, check out something much simpler: Jeremy Ashkenas' delightfully readable [Journo](https://github.com/jashkenas/journo), a single-file, Node-based tool that deploys via rsync.

## The problem: Some interactivity

We are talking about [Sprinkles of JavaScript](/railsconf-2013-keynotes-rails-4-vs-ember-dot-js), not RIA: Most content is navigated through good old fashioned full-page reloads, but engaging the user
requires scattered elements of interactive behavior and dynamic content.

## The current solution: Third-party widgets and services

The ultimate example of a cross-site-loaded, service-backed widget may be [Disqus](http://disqus.com), which is so popular for static blogs that it is a default in Octopress. On product and marketing sites, no doubt you have seen countless feedback and survey widgets. [UserVoice](https://www.uservoice.com) is one example.

### Pros - Third-party service

* Easy to integrate
* Mature, complete, and ready

### Cons - Third-party service

* Third-party branding
* Difficult or impossible to customize
* Vendor lock-in
* [Ugly ads](http://ruby.learncodethehardway.org/book/ex2.html) or monthly fees

## A better solution: Open-source widgets and Backend as a Service (BaaS)

With taglines like "Build apps fast without managing servers," there are already a number of commercial BaaS offerings.

* [Firebase](https://www.firebase.com)
* [Parse](https://www.parse.com) (acquired by Facebook on April 25, 2013)
* [Kinvey](http://www.kinvey.com)
* [Kii](http://www.kii.com)
* [StackMob](https://developer.stackmob.com)

Please let me know if somehow I missed including your favorite JavaScript-supporting BaaS!

### Pros - Commercial BaaS

* Generalized, flexible
* Free tier is plenty for small stuff
* Allow integration across your widgets
* OAuth or custom auth
* Fine-grained control over your data

### Cons - Commercial BaaS

* Not portable to alternative hosting
* Obfuscated/closed source makes it hard to debug
* Except Firebase, most are primarily for native mobile apps
* VC-backing: acquisition or death?

## The Dream: 100% FLOSS BaaS

Not much yet, [helios.io](http://helios.io) (Ruby, iOS clients only) seems promising, especially since it has backing from Heroku.

Some others I found by looking around are [BaasBox](http://www.baasbox.com) (Java), [End.js](https://github.com/demohi/end)
(docs not in English), and [smooth.io](https://github.com/datapimp/smooth) (a work in progress).

## Why I care about this stuff

* Marketing sites - Make one the day you get your idea
* [Email landing page](https://github.com/quartzmo/email-landing-page) - My earlier concept of a "minimalist" solution (Heroku, Sinatra, and Mailchimp)
* [backbonecoffeescript.com](http://backbonecoffeescript.com) - A rudimentary landing page with some dynamic content via [Storify](https://storify.com/)
* Interactive books - My platform: [scriptybooks.com](http://www.scriptybooks.com)