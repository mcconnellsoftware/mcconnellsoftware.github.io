---
layout: single
title:  "Blogging for Hackers"
date:   2018-03-18 12:21:29 +0000
tags: Tech
header:
  image: /assets/images/header_wave.jpg
---
Blogging: simple enough, you have an idea of potentially at least _some_ originality, and write about it a bit. Easy. Wordpress and a bunch of other great tools and sites mean anyone who wants to put their thoughts down to share with others can do so.

But where's the *challenge* in that!

Having long been tempted - for bandwidth and performance reasons related to an iffy self-hosted option - to move to GitHub Pages, which seem to work well with a site generator called Jekyll, I figured I'd look into it in more depth, and long story short: here we are, a new blog platform, and a very hacker friendly workflow!

Some key aspects worth mentioning:
- GitHub Pages serves essentially *static* content, it's not somewhere you can run JSP or Servlets or any other application content
- it does however work well with the aforementioned Jekyll which lets you produce content as Markdown text then "generate" your website: combine all your content .md files with your various config and layout settings to produce polished HTML - CSS, image and JS assets included
- GitHub Pages sits on top of your normal GitHub repo (albeit be aware of the strict naming convention you need to follow, it's well highlighted so let's not over-elaborate here), meaning you get all the normal benefits of version control - diffs of versions, ability to rollback, etc
- Jekyll's built with Ruby and its ecosystem is primarily Linux based but there are Windows workarounds - personally I went the route of installing a Linux subsystem on my Windows 10 desktop machine and other than having the same weird inter-module dependency issues reported by many other Ruby users at Stack Overflow, it's gone pretty well so far
- working with Plain Old Text Files is great if you're used to working with source code anyway - no buggy wysiwyg to fight with!
- working with a toolchain of Git, preferred IDE (IntelliJ IDEA right now), and a Linux based preview server is truly a pleasure
- the ability to run Jekyll locally makes for a workflow really similar to that in actual software development: develop and test locally, find problems quickly, and commit/push when you're satisfied - this is definitely A Good Thing!   

There are some minor gotchas to be aware of:
- getting the whole local Linux, Ruby stuff going properly on Windows 10 can be fiddly: random "libcurl.so not found" errors could be a showstopper for the less technically adept 
- local-deploy vs remote-hosted situations require _mutually exclusive config changes_ to theme and Gem settings; in practice this means get your basic config files up and working for GitHub Pages use, then simply _don't commit/push them_ when running locally, just commit your content changes 
- working to visual themes is much less "switch at the press of a button" than Wordpress; find one you really like and then stick with it while you learn and understand the system, while being aware if you do want to change in the future it might be a lot more involved than you'd like - layout names will vary, features will be unrecognised and produce errors, etc

All in all, I find it an excellent end-to-end platform and now look forward to resuming my twice yearly posting pattern!

Links/further reading:

[GitHub Pages](https://pages.github.com/)  
[Jekyll](https://jekyllrb.com/docs/github-pages/)  
["Minimal Mistakes" theme - used here](https://mmistakes.github.io/minimal-mistakes/)  
[Full range of Jekyll themes](http://jekyllthemes.org/)  

And of course feel free to [explore my own repo](https://github.com/mcconnellsoftware/mcconnellsoftware.github.io) to see what config choices I've made, etc
