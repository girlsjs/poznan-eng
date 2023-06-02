# "Wyprawy kosmiczne" Space expeditions girls.js repository Poznan


### Config
Site configuration uses Github Pages and Jekyll page builder (available by default with Github Pages).

Github Actions perform build & deploy in the `.github/jekyll-gh-pages.yml` file. In addition, the template settings are located in `_config.yml`.

Templates from jekyll: https://jekyllrb.com/docs/pages/

All additional information on how to use the template can be found in the `THEME.md` file in the docs folder.


### How to add pages?

In brief:

The manual is divided into `_pages` subpages - subsequent chapters of the workshop.

All workshop chapters must be in **markdown** format and placed in the `_posts` folder. In addition, the files **must have a properly formatted header** (important to be correctly displayed).

```md

---
title: Why JS?
author: Rita Lyczywek
date: 2023-04-27 
category: programming
layout: post
cover: ../assets/cover.png
---

```

- obligatory: title, layout
- optional: author, date, category, cover


Posts are sorted automatically by chapter number - please keep the convention
