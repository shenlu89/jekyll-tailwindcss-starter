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

I use **Ubuntu** as defualt platform to build my blog. So I need run this command to create a empty scaffold.

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

We could see that `Gemfile` is not included by default. We need to create our own `Gemfile` at the root of the project. which can help you manage Jekyll verison and plugins.

```ruby
source "https://rubygems.org"
# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
gem "jekyll", "~> 4.2.0"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-paginate", "~> 1.1.0"
  gem "jekyll-seo-tag", "~> 2.7.1"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
# install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
#   gem "tzinfo", "~> 1.2"
#   gem "tzinfo-data"
# end

# Performance-booster for watching directories on Windows
# gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?
```

### Serve Jekyll locally

Now you can build this site and make it available on a local server.

```sh
cd your_website_name
bundle exec jekyll serve
```

After starting successfully, you can browse it to <http://localhost:4000> locally.

![]({{ site.github.url }}/assets/images/your_website_name.png)

It's very simple. That's all.