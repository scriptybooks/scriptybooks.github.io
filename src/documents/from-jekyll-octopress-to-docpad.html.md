```
title: From Jekyll/Octopress to DocPad
layout: post
tags: ['post']
date: 2013-05-12
author: Chris Smith (@quartzmo)
```

After just three posts on [Octopress](http://octopress.org/), I decided to migrate [ScriptyBlog](/) to [DocPad](http://docpad.org/). Why? I'm trying to find the best platform for authoring interactive online technical books, for the next version of [ScriptyBooks](http://www.scriptybooks.com).

Jekyll (on which Octopress is based) is a mature static site generation tool, that has had a recent [1.0 release](http://blog.parkermoore.de/2013/05/06/jekyll-1-dot-0-released/) and is again enjoying active development. However, [Jekyll](http://jekyllrb.com/) is Ruby-based, while DocPad runs on Node.js and is written in CoffeeScript, Backbone.js, and Eco templates. Just like my own interactive [Backbone.js + CoffeeScript](http://www.scriptybooks.com/books/backbone-coffeescript) book!

It took me a few hours to do the migration. Here are my notes:

1. Update Node.js and npm. This is easy these days with the official installer.
1. Follow the install instructions. Node [tiny modules](http://substack.net/many_things) are for real. You may find it delightful, or alarming, to watch the npm install of DocPad.
1. I reacted with shock and shut down my network connection when I realized the `docpad run` script was reporting back to the mother ship. After looking into the source code and thinking about it a bit, I decided this was okay.
1. Follow the Quick Start instructions for a bare install. So far, so good.
1. In a new directory, create a new project using an existing skeleton. After looking at the list of plugins used in several skeletons, I went with Twitter Bootstrap.
1. Copy over a post source file from the Octopress project. If post doesn't show up in the list, it may be because you omitted the 'post' tag that the DocPad example posts include. The 'post' tag is used in a query and is required.
1. Encounter the EMFILE 'too many open files' error. Waste time googling and tinkering before finally finding the correct solution in the [DocPad troubleshoot page](http://docpad.org/docs/troubleshoot). Renew my vow to always RTFM.
1. Since file watching on OS X doesn't seem to be working very well, follow troubleshoot page solution for switching to 'watchFile'. The result is noticeably better though still not perfect. The [livereload](https://github.com/docpad/docpad-plugin-livereload) plugin works well for me.
1. Install the Highlight.js plugin for code highlighting. Plugin management with npm is awesome!
1. Convert Jekyll/Octopress image helper to markdown.
1. Customize Bootstrap. Replace `style.css.styl` with `style.css.less` and uninstall stylus plugin. Stylus may be cool, but on a Bootstrap project I think it makes sense to stick with Less.
1. Find Ben Delarre's helpful post on [creating an index page](http://delarre.net/posts/creating-the-index-page.html) and use it to make something like the Octopress index page. So far so good with CoffeeScript and Eco!
1. Run `docpad generate --env static` and compare output against Octopress. It's different of course, but looks good.
1. Waste time trying to figure out how to push `out` directory from master as the top-level directory on GitHub. It turns out the ghpages plugin already takes care of this.
1. Fiddle with git to restore the blog source to the `master` branch. (Octopress uses a `source` branch.)
1. Deploy using the ghpages plugin with `docpad deploy-ghpages`. See the glorious site live for a minute or so. Then see a GitHub 404 page.
1. Figure out that I forgot to copy [the CNAME file](https://help.github.com/articles/my-custom-domain-isn-t-working) from the Octopress blog to the DocPad `src` directory. Deploy again.
1. Success!

If you have any DocPad expertise to share, give me a shout on Twitter ([@quartzmo](http://twitter.com/quartzmo)).