---
layout: post
title: "Jekyll with plugins and Github Pages"
description: ""
category:
tags:
  - jekyll
  - github
  - githubpages
---

Github skips running scripts in **_plugins** directory due to security
considreations. But you can push pre-built site into master branch:

* make **src** branch
* remove everything from `destination` directory (_site)
* clone this repository again into `destination` directory. Now you have **master** branch in your `destination` directory.
* clear `destination` directory again and build your jekyll site.
* go to `destination` directory, commit and push changes. Now your site is
  ready.

_Your `destination` folder should be gitignored_

Do not forget to push your changes in **src** branch
