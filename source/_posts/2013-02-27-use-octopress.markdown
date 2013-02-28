---
layout: post
title: "介绍一下octopress的使用"
date: 2013-02-27 18:07
comments: true
categories: 

---

octopress的自己的标题*A blogging framework for hackers.*就很霸气,我很喜欢.

官方网站:<http://octopress.org/>

###前期准备

####1.安装git

*git的使用,在以后为大家介绍,先安装能使用了*

**快捷安装:**

* Mac的安装

{% codeblock %}
brew install git
{% endcodeblock%}

* Ubuntu的安装

{% codeblock %}
sudo apt-get install git git-core
{% endcodeblock %}

* Windows的安装

  下载一个git,下一步就ok了

####2.安装ruby

简单安装ruby参考:
<http://fblog.fanaifan.com/blog/2013/02/27/first-post/>

###开始octopress的旅程

####1.下载octopress

{% codeblock %}
git clone git://github.com/imathis/octopress.git octopress
cd octopress    # If you use RVM, You'll be asked if you trust the .rvmrc file (say yes).
ruby --version  # Should report Ruby 1.9.3
{% endcodeblock %}

####2.安装octopress依赖

{% codeblock %}
gem install bundler
rbenv rehash    # If you use rbenv, rehash to be able to run the bundle command
bundle install
{% endcodeblock %}

####3.安装默认主题

{% codeblock %}
rake install
{% endcodeblock %}

####4._config.yml的主要设置

{% codeblock %}
url:                # For rewriting urls for RSS, etc
title:              # Used in the header and title tags
subtitle:           # A description used in the header
author:             # Your name, for RSS, Copyright, Metadata
simple_search:      # Search engine for simple site search
description:        # A default meta description for your site
date_format:        # Format dates using Ruby's date strftime syntax
subscribe_rss:      # Url for your blog's feed, defauts to /atom.xml
subscribe_email:    # Url to subscribe by email (service required)
category_feeds:     # Enable per category RSS feeds (defaults to false in 2.1)
email:              # Email address for the RSS feed if you want it.
{% endcodeblock%}

####5.jekyll&插件

{% codeblock %}
root:               # Mapping for relative urls (default: /)
permalink:          # Permalink structure for blog posts
source:             # Directory for site source files
destination:        # Directory for generated site files
plugins:            # Directory for Jekyll plugins
code_dir:           # Directory for code snippets (for include_code plugin)
category_dir:       # Directory for generated blog category pages

pygments:           # Toggle python pygments syntax highlighting
paginate:           # Posts per page on the blog index
pagination_dir:     # Directory base for pagination URLs eg. /blog/page/2/
recent_posts:       # Number of recent posts to appear in the sidebar

default_asides:     # Configure what shows up in the sidebar and in what order
blog_index_asides:  # Optional sidebar config for blog index page
post_asides:        # Optional sidebar config for post layout
page_asides:        # Optional sidebar config for page layout
{% endcodeblock %}

####6.第三方插件

* **Github** - *List your github repositories in the sidebar*
* **Twitter** - *Setup a sidebar twitter feed, follow button, and tweet button (for sharing posts and pages).*
* **Google Plus One** - *Setup sharing for posts and pages on Google’s plus one network.*
* **Pinboard** - *Share your recent Pinboard bookmarks in the sidebar.*
* **Delicious** - *Share your recent Delicious bookmarks in the sidebar.*
* **Disqus Comments** - *Add your disqus short name to enable disqus comments on your site.*
* **Google Analytics** - *Add your tracking id to enable Google Analytics tracking for your site.*
* **Facebook** - *Add a Facebook like button*

###开始我们的blog计划吧

####先记住常用命令

`依机器环境的执行rake的时候,需要添加bundle exec`

**创建一篇文章**

语法

{% codeblock %}
rake new_post['title']
{% endcodeblock%}

例子

{% codeblock %}
rake new_post["Zombie Ninjas Attack: A survivor's retrospective"] 
 # Creates source/_posts/2011-07-03-zombie-ninjas-attack-a-survivors-retrospective.markdown
{% endcodeblock %}

**创建一篇页面**

语法

{% codeblock %}
rake new_page[super-awesome] # creates /source/super-awesome/index.markdown
rake new_page[super-awesome/page.html] # creates /source/super-awesome/page.html
{% endcodeblock%}

**生成和预览**

{% codeblock %}
rake generate   # Generates posts and pages into the public directory
rake watch      # Watches source/ and sass/ for changes and regenerates
rake preview    # Watches, and mounts a webserver at http://localhost:4000
{% endcodeblock%}

**初始化**

{% codeblock %}
rake setup_github_pages
{% endcodeblock%}

**发布博客**

{% codeblock %}
rake deploy
{% endcodeblock%}







