---
layout: post
title: How to Make a Jekyll Github Website with Existing Template


categories:
  - Technology
tags:
  - Github

---


I was thinking to make a personal website and host it on the Github. But I am not sure how to do at the beginning. After searching for lots of resources, I figured out how to use an existing template (so-simple) to make my personal website. 

First, I found the so-simple template published by Michael Rose (mmistakes) Github. 

[so-simple template Github link](https://github.com/mmistakes/so-simple-theme)

In the README file, you could see how to set it up. If you're running Jekyll v3.5+ and self-hosting you can quickly install the theme as a Ruby gem. 

## Ruby Gem Method

1. Add this line to your Jekyll site's Gemfile (or create one):

> gem "jekyll-theme-so-simple"

2. Add this line to your Jekyll site's _config.yml file:

> theme: jekyll-theme-so-simple

3. Then run Bundler to install the theme gem and dependencies:

> bundle install