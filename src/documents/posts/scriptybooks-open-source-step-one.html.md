```
title: "ScriptyBooks open source: step one"
layout: post
tags: ['static sites','open source']
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


csmith:scriptybooks.github.io vitalvu$ git status
# On branch master
# Your branch is ahead of 'octopress/master' by 5 commits.
#
nothing to commit (working directory clean)
csmith:scriptybooks.github.io vitalvu$ git checkout source
Switched to branch 'source'
Your branch and 'origin/master' have diverged,
and have 5 and 5 different commits each, respectively.


The messages about the branches diverging are nothing to worry about. They just show you've been busy with your blog.

### What do you think?

Is Jekyll the right approach for writing interactive Web books? Please leave a comment. Oooops you can't, because I didn't
enable the Disqus plugin (I can't stand the ads that Disqus has been showing.) I'm thinking it'd be cool to have a comment widget that
uses [Firebase](http://www.firebase.com). What about that idea? Anyone want to help? Arrggh, until I have it done, you still can't comment. (Tweet me [@quartzmo](http://twitter.com/quartzmo) instead.)
