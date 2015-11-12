---
layout: post
title:  "Jekyll Frustrations"
date:   2015-11-12 09:10:53 -0500
categories: jekyll update
---
Maybe it's not such a great idea to try to deploy a Jekyll site while on a train before 9am.

I dig Jekyll. Here are my favorite parts about Jekyll:

1. It's free and open-source.
2. Comes with Sass support out of the box. While I've been more into OOCSS recently, this is still cool and relatively painless to setup because you don't need a compilation tool like Gulp or CSSNext or Grunt or whatever tool you like.
3. Static files = fast experience for users
4. No need to worry about databases

Here are my least favorite parts:

1. Deployment. By default the site gets built (using `jekyll build` command) into the `_site` directory. I'm good with this so far. This directory is your site in its entirety, based on your content, configs, assets, etc etc – but this directory is ignored by git. This kind of makes sense. Typically, you don't want to track generated files in git. My main frustrations come from the process of deploying this directory alone to the `gh-pages` branch in a sane fashion.

### What's solution?
I'm not sure this is even a great solution.

Scenario: deploy your site (a Project Page) to `gh-pages` branch.

Solution:

1. Stop ignoring `_site` folder. I know, I know...
2. From the master branch `jekyll build && git subtree push --prefix _site origin gh-pages`

I'd love to hear what you're doing here – this feels wrong.
