```
title: Static Site Generation with Node.js and CoffeeScript
layout: post
tags: ['post']
date: 2013-05-28
author: Chris Smith (@quartzmo)
```
*This article was originally published on [coffeescriptlove.com](http://www.coffeescriptlove.com/2013/05/static-site-generation-with-nodejs-and.html).*

As I discussed in ["Interactive Static Sites With Jekyll, Backbone.js, and Firebase"](http://blog.scriptybooks.com/interactive-static-sites-with-jekyll-backbone-js-and-firebase/), static sites built using powerful Ruby-based tools such as [Jekyll](https://github.com/mojombo/jekyll) and [Middleman](https://github.com/middleman/middleman) are surging in popularity based on their benefits: low hosting costs, speed, stability, and security. Jekyll has powered [the Obama campaign's $250 million fundraising platform](http://kylerush.net/blog/meet-the-obama-campaigns-250-million-fundraising-platform/) as well as a [new version of healthcare.gov](http://developmentseed.org/blog/new-healthcare-gov-is-open-and-cms-free/). Several months ago GitHub Co-Founder and CEO Tom Preston-Werner [renewed his commitment to Jekyll](https://github.com/mojombo/jekyll/issues/578#issuecomment-11414645), writing, "Sorry for not keeping this thing moving faster. 2013 is gonna kick ass. Wake up, go to war."

So, this certainly sounds like good news for rubyists. But is there a tool for creating static sites using Node.js and CoffeeScript?

Say hello to [DocPad](http://docpad.org/).

![docpad home page](/images/docpad-benefits.jpg)

DocPad embraces CoffeeScript in a big way. 

For starters, let's take a look at a typical [DocPad configuration file](https://github.com/docpad/kitchensink.docpad/blob/master/docpad.coffee). Whoa! Not only is it in CoffeeScript, it even contains functions. In my opinion, as long as you use this feature judiciously, the ability to house short, deliciously-readable CoffeeScript functions in your configuration is really nice. For an interesting example of configuration, check out the instructions for using [DocPad, GitHub and Prose as a Wiki](https://gist.github.com/balupton/5519403). (Aside: After I've published this post, I will employ [Prose](http://prose.io) and GitHub in this very way to add a link to my post to the official DocPad site.)

The [DocPad core](https://github.com/bevry/docpad) and almost all of its [community plugins](https://github.com/docpad) are written in CoffeeScript, but that's not all. Although DocPad supports [a long list of renderers](http://docpad.org/docs/plugins#renderers) that includes Handlebars and Jade in addition to PHP and Ruby, the project's [skeletons](http://docpad.org/docs/skeletons) have a strong preference for [Eco (Embedded CoffeeScript)](https://github.com/sstephenson/eco) templates. For an example of a typical page, check out [getting-started.html.eco](https://github.com/docpad/kitchensink.docpad/blob/master/src/documents/pages/getting-started.html.eco).

If you enjoy CoffeeScript and Eco (it also uses Backbone.js), I encourage you to jump in and give DocPad a try. I have posted [my notes](http://blog.scriptybooks.com/from-jekyll-octopress-to-docpad/) about porting [blog.scriptybooks.com](http://blog.scriptybooks.com) from Jekyll to DocPad, in case they might be of use.
