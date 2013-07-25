```
title: Landing Page with Yeoman, Bower, Grunt, and a Node API Server
layout: post
tags: ['post']
date: 2013-06-20
author: Chris Smith (@quartzmo)
```
After building some static sites with [Jekyll](http://blog.scriptybooks.com/interactive-static-sites-with-jekyll-backbone-js-and-firebase/) and then [DocPad](http://blog.scriptybooks.com/static-site-generation-with-node-js-and-coffeescript/), I decided that it might make sense to leverage [Grunt](http://gruntjs.com/) for the multitude of build steps such as asset minification and CoffeeScript compilation, rather than tool-specific plugins. This was confirmed by briefly working on my own DocPad plugin for downloading Web components, an effort that led me back to [Bower](http://bower.io/), which despite some [flaws](https://twitter.com/maccaw/status/335537034309533697) has been growing in popularity as a package manager for the Web.

Well, if you want to quickly scaffold a Grunt and Bower project, it turns that the new [Yeoman](http://yeoman.io/) (1.0) makes it very easy to do. To get started, I used `yo webapp` to redo a simple [landing page for an AngularJS book](http://www.angularjsbook.com/) that I'm considering writing. This was easy, although the [Grunt build](https://github.com/quartzmo/angularjsbook.com/blob/master/Gruntfile.js) produced by the [Yeoman webapp generator](https://github.com/yeoman/generator-webapp) contains far too much testing  ([Mocha](http://visionmedia.github.io/mocha/), [PhantomJS](http://phantomjs.org/)) for such a simple page.

Taking time out to reflect on the slowness of the build, I tried out two non-Grunt Node site generators: [Jared Hanson](https://twitter.com/jaredhanson)'s [Kerouac](https://github.com/jaredhanson/kerouac/) and [Jeff Escalante](https://twitter.com/jescalan)'s [Roots](http://roots.cx/). Both are lean and blazing fast, but do not leverage a larger ecosystem of plugins or components. However, I will almost certainly come back to both of them.

Continuing with Yeoman, I decided to build a somewhat more ambitious single-page site, with a small [Backbone.js](http://backbonejs.org/) widget for signups backed by a light Node JSON API server. (I coded and deployed the server separately, although in the future I hope to mostly generate the server code from the front-end project.) Here is the finished result: The [TacoConf Salt Lake City](http://www.quartzmo.com/tacoconfslc/) landing page.

![tacoconfslc landing page](/images/taco_conf_who_is_going.jpg)

Things went smoothly at first. Adding Backbone using Bower was very easy, although the Underscore dependency was [not handled automatically](https://github.com/bower/bower/issues/172). (This made me [think about using Browserify instead](http://www.coffeescriptlove.com/2013/06/coffeescript-in-chrome-devtools.html) for JavaScript components.) But things got difficult when I needed different server host names for production and development. Yeoman's [grunt-usemin](https://github.com/yeoman/grunt-usemin) plugin felt extremely limiting. I cobbled together a solution to the problem with [grunt-config](https://github.com/outaTiME/grunt-config) and [grunt-replace](https://github.com/outaTiME/grunt-replace), but it made me seriously miss the power of a template-based asset pipeline such as the one provided by DocPad.

One of the better ideas I picked up from Yeoman is using [git subtree for deployment](https://github.com/yeoman/yeoman/wiki/Deployment) to GitHub Pages. On Mac/OS X, you currently need to re-install git with homebrew to get subtree, but it's worth it. 

Next in my lineup for static site generation with Grunt: [Assemble](https://github.com/assemble/assemble).
