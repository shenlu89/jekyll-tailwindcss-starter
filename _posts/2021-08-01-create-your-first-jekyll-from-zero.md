---
layout: post
title: Build Your First Jekyll Website from Zero
subtitle: How to build a Jekyll website and setup its configuration
date: 2021-08-01 18:05:55 -0500
image: '/assets/images/githubjekyll.png'
---


Hi there, today I will talk about how to build a jekyll website from zero to one. There are only 3 steps:

1. Install Jekyll
2. Create a scaffold of Jekyll
3. Serve this scaffold locally

### Install Jekyll

Jekyll is cross-platform software, so you can run it in Linux, MacoS and Windows. However, before you use it, you should install all prerequisites, which you can cheek on this [page](https://jekyllrb.com/docs/installation/#requirements). And after getting that done, you can install Jekyll now.

```sh
gem install jekyll bundler
```

### Create a scaffold

I use **Ubuntu** as my developing platform. To create a empty scaffold, I just run this command.

```sh
## Creates scaffolding but with empty files
jekyll new your_website_name --blank
```

### Take a look the scaffold

The structure of scaffold looks like below.

```sh
.
├── assets
│   └── css
│       └── main.scss
├── _config.yml
├── _data
├── _drafts
├── _includes
├── index.md
├── _layouts
│   └── default.html
├── _posts
└── _sass
    └── main.scss
```

### Serve Jekyll locally

Now you can change into your new directory and make it available on a local server.

```sh
cd your_website_name
bundle exec jekyll serve
```

After serving it, you can browse it to <http://localhost:4000> locally.

It's very simple. That's all.