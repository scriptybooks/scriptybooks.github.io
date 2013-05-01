---
layout: post
title: "RailsConf 2013 keynotes: Rails 4 vs Ember.js"
date: 2013-04-30 20:12
comments: true
categories:
author: Chris Smith (@quartzmo)
---

{% img /images/posts/railsconf_2013_wycats_jessabean.png %}

*Image source: https://twitter.com/jessabean/status/329299671728136193*

## Recap

Here's a quick recap of the RailsConf 2013 keynotes from David Heinemeier Hansson (DHH) and Yehuda Katz:

First, David explained his firm commitment to server-side programming and provided an overview of Russian-doll caching, turbolinks, JavaScript helpers, and other details. The content of his keynote
was remarkably similar to his blog post of over a year before, [How Basecamp Next got to be so damn fast without using much client-side UI](http://37signals.com/svn/posts/3112-how-basecamp-next-got-to-be-so-damn-fast-without-using-much-client-side-ui).

Yehuda's keynote was an energetic, well-researched rebuttal to David's that included many memorable sound-bites, such as
"2012: The Year Rubyists Wrote Off JS Libraries." I'll update this post with a link to it when it becomes available on ConFreaks, as it's so worth watching.

## Themes

As the two sought to differentiate their approaches to modern Web apps, I found myself interested in three major themes.

The first theme, **mental model**, is simply where your mind lives when you program your application. Are you writing Rails for the server or
JavaScript for the client? This is pretty much a matter of taste, but as you can imagine, in the heart of Rubyland the burden of proof was
on Yehuda for this one. It was enough for David to simply state something to the effect of Ruby being better.

The second theme is the **organization** of JavaScript--or the lack of it, as Yehuda would point out, blaming the "Sprinkles of JavaScript"
mentality for much *ad hoc* JavaScript programming. Unfortunately, David has never revealed much about the substantial
CoffeeScript portion of Basecamp, except to say that of the 10k or so lines of code, roughly a third is the
Backbone-based calendar (a client-side app). Rails 4 will not provide any new facilities for organizing client-side code,
as far as I know, which is a disappointment considering the innovations of the Rails Asset Pipeline. In this contest, which is really
one of clarity and elegance, Yehuda's vision is the stronger.

The third theme is the most technical and also by far the most interesting for me personally. This is the question of where to **render HTML**, on the server or the client, and the implications of that decision for performance. I thought the best part of David's keynote was when he argued that the great strength of HTML is
its orientation toward documents, and further, that many web applications are appropriately document-centric. He provided examples of how small
user-specific variations in documents could be made on the client, allowing a single master representation to be cached for all users on the server.
Yehuda, arguing for rendering to be done on the client from JSON delivered from the server, attempted to use David's examples as evidence that significant JavaScript programming is still required, and urged the audience to "embrace JavaScript."

## My Conclusions

As usual, I enjoyed Yehuda's keynote immensely and agreed enthusiastically with almost everything he said while he was saying it. He is really such a great speaker.

But as I
reflected afterward on his evidence for client-side rendering, I felt that something was amiss. The little modifications, changing a date to local time or showing an admin link, were exactly that, little changes. What David implied made sense to me, that in document-centric domains (he excluded games), the bulk of value in a document should not require dynamic modification. If a high-enough percentage of
web content is exactly the same for all users with access to the web resource, then it really makes sense to do the rendering *once* on the server,
cache the result, and save clients the trouble and time of rendering *all* of the content using JavaScript. And I wonder what that "high-enough" number really is? In the end, it may just be whatever you're hoping to first see as your underpowered device loads the page over a slow connection.

Yehuda's approach has elegance on its side, while David's is a much uglier hybrid. But the hybrid appears to have
serious performance advantages. If you haven't already, you must read about Twitter's experience with and partial retreat from client-side rendering in the ["time to first tweet"](http://engineering.twitter.com/2012/05/improving-performance-on-twittercom.html) post of May 29, 2012.

As always, a one-size-fits-all, one-tool-for-every-job approach is likely to lead to trouble. So you need to ask yourself, how document-oriented is
your application?

Why does this matter to [ScriptyBooks](http://www.scriptybooks.com)? An interactive, online book is at a far end of the spectrum. So far in fact that although the current implementation is based on Rails, I am experimenting with how [it might one day be a static site](/scriptybooks-open-source-step-one).

If you have any thoughts, please comment below via my new open-source/Firebase alternative to Disqus, [Discussion.js](https://github.com/quartzmo/discussion).