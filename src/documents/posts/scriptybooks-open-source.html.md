```
title: ScriptyBooks open source
layout: post
tags: ['intro','post']
date: 2013-04-15
```


I've been intending to open-source the important parts of the ScriptyBooks stack since the beginning, but I never felt
right about sharing it as a Rails app. My original *bookserver* was a simple Node.js app and a command-line build tool, and that seemed like a
better path for open source, although I didn't get far down it before practical concerns on the business side led me to
switch to Ruby, Nokogiri, and Rails.

### Enter the Jekyll

[Octopress](http://octopress.org) + [Jekyll](http://jekyllrb.com/) is pretty cool stuff. Out of the box, the default blog doesn't look like much....
but the cmd-line blogging tool is solid. It leverages git and GitHub to the max.
[Deploying](http://octopress.org/docs/deploying/github/) to [GitHub Pages](http://pages.github.com/) is dialed in with its own `source` branch.
Octopress even includes tasks for updating from the original project:
Here's how you [update the software](http://octopress.org/docs/updating/), all git based. I should have clued into this stuff a long time ago.

I think the git usage will impress you. Here's a little taste of the experience:

# live

This is why Windows 8’s poor performance matters. It was an attempt to solve the innovator’s dilemma by creating an operating system and a user interface for both PCs and mobiles. Mr Ballmer hoped that consumers would want to move effortlessly from PCs to tablets to smartphones—and that Microsoft would be able to invade the mobile markets while simultaneously reigniting demand for its core PC products. But so far the reverse has happened: Microsoft has reinforced suspicions that it does not understand hand-held devices while simultaneously alienating its core PC users. It is possible that Microsoft will be able to solve this problem with future iterations of Windows 8. But it is looking likely that the two types of device need different operating systems. Microsoft’s biggest rival, Apple, has kept the two devices separate. That bodes ill for Mr Ballmer’s strategy.

Blocks are a way for plugins and even ourselves to be able to easily add scripts, styles and meta elements to our pages. In the instance of the Live Reload Plugin, it needs the Script Block to be able to inject the needed scripts into the page so it can refresh browser whenever changes are made.

So to add the three default blocks to our layout, we'll update our layout to become: