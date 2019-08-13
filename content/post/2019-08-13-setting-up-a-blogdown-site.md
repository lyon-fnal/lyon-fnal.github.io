---
title: Setting up this Blogdown site
author: Adam
date: '2019-08-13'
slug: setting-up-this-blogdown-site
categories:
  - R
tags: []
subtitle: ''
summary: ''
authors: []
lastmod: '2019-08-13T01:41:45-05:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

Setting up this [Blogdown](https://bookdown.org/yihui/blogdown/) site was way more complicated that I thought it would be. Mostly because I was trying to use someone else's page as an example, but Hugo and the Academic theme have changed enough that many of the things he does do not work in this later version. The documentation is also not as clear as it needs to be to do things quickly. But in the end, it works and it looks pretty nice. Here are some tips that I learned,

* Do not use someone else's site for examples. If they are using an older version of Hugo or the Academic theme, things they do will not work and you'll get blank or unformatted pages for no discernible reason. 
* Better to carefully read the Academic theme [documentation](https://sourcethemes.com/academic/docs/). It follows a tutorial format, so if you have a specific question it's hard to find the answer - but it's there.
* The Blogdown [documentation](https://bookdown.org/yihui/blogdown/) is lacking in detail. There are some tutorials online that are good for getting started, such as the `Advanced R Markdown Workshop` [tutorial](https://arm.rbind.io/days/day1/blogdown/) at *rstudio::conf 2019* (see [here](https://blog.rstudio.com/2019/02/06/rstudio-conf-2019-workshops/) for a list of all talks and tutorials).
* Github is serving the site. It wasn't easy to find out how to set that up. This [post](https://www.hjdskes.nl/blog/deploying-hugo-on-personal-gh-pages/) is what worked and the two-branch solution, while a little clumsy, is pretty straightforward.
* At one point I included a talk that was a large PDF file and tried to push that to Github. Github rejected the push as the file exceeded their size limits. Getting that file out of my git history proved to be impossible (despite trying many tricks with `git filter-tree`). I eventually deleted my local repository entirely and just cloned it again from Github. Luckily, I didn't have that many changes and were able to keep those files. 

Here are some items I don't want to forget,

* Personal information, including the bio, goes in `content/authors/admin/_index.md`
* Menu items are in `config/_default/menus.toml`
* Files in `content/home` are widgets that may appear on the home page (controlled by the `active` flag). To link to such widgets in the menu, use `#filename_base` like `#posts`. 
* To link to a "section", e.g. a directory in `content`, use `section/` like `talks/`. 
* The main configuration is in `config.toml`, but some things are in `config/_default/params.toml` like `sharing`. 
* The `public` directory needs to be committed and pushed or else the `subtree` won't work. 

That's it!


