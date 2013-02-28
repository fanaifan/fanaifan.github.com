---
layout: post
title: "拥有一个属于自己github pages"
date: 2013-02-27 16:26
comments: true
categories: 

---

**用了很久终于能在github上有了这第一篇博客,不能说是很高兴,至少自己很满足.**

下面和大家分享一下,我弄的这个博客的过程.

先介绍一下,我的机器系统环境:Mac OSX 10.8.2

> 如果大家不是Unix系列系统也没有关系,操作差异也不是很大.但是建议使用Linux系统,比如Ubuntu,ArchLinux

**首先介绍一下需要安装的环境**

1.ruby,一种语言,这个不用介绍了

2.jekyll是ruby的一个gem,同时我们主要用这个来写我们的博客

3.rdiscount用来解析markdown的


##首先准备环境

###1. ruby的安装

{% codeblock %}
curl -L https://get.rvm.io | bash -s stable
sudo rvm install 1.9.3
rvm use 1.9.3
ruby -v
rvm --default 1.9.3
{% endcodeblock %}

###2. Jekyll的安装

{% codeblock %}
sudo gem install jekyll
{% endcodeblock %}

> 小建议:由于国内网络原因（你懂的），导致 rubygems.org 存放在 Amazon S3 上面的资源文件间歇性连接失败,你可以先执行下面的命令在安装jekyll

{% codeblock %}
$ gem sources --remove https://rubygems.org/
$ gem sources -a http://ruby.taobao.org/
$ gem sources -l
*** CURRENT SOURCES ***

http://ruby.taobao.org
{% endcodeblock %}

###3.安装rdiscount来解析markdown语言

{% codeblock %}
sudo gem install rdiscount
{% endcodeblock %}

###4.pygments--支持语法高亮，要装python 

`这个可以选装,一开始不安装这个不影响你写博客`

{% codeblock %}
sudo port install python25 py25-pygments
sudo ln -s <py25-pygments> <pygments>
{% endcodeblock %}

**ok,到这里环境基本准备齐了,该开始干活了**

如果没有什么好的模板可以借鉴一下大师们的
<https://github.com/mojombo/jekyll/wiki/Sites>

###介绍一款写markdown的神器: Mou
![Mou icon](http://mouapp.com/Mou_128.png)


###**下面为大家推荐几篇比较好的文章:**

创建github账户 <http://www.worldhello.net/gotgithub/02-join-github/010-account-setup.html>

用Jekyll构建静态网站 <http://yanping.me/cn/blog/2011/12/15/building-static-sites-with-jekyll/>

在github pages绑定自己的域名 <https://help.github.com/articles/setting-up-a-custom-domain-with-pages>

_介绍一款jekyll的框架octopress,很不错哦,下篇给大家絮叨一下._


