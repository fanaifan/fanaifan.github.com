---
layout: post
title: "cloudfoundry 域名绑定"
date: 2013-04-10 21:22
comments: true
categories:
 
---

### 用一种不同的方式将自己的域名绑定到cloudfoundry

* 申请一个免费空间:<http://www.awardspace.com>

* 将要绑定的域名先添加到免费空间

* 再将域名指向免费空间提供的A地址

* 用ftp登陆免费空间添加一个.htaccess文件

   `.htaccess内容`
   
 {%codeblock%}
  <IfModule mod_rewrite.c>
	RewriteEngine on
	RewriteBase /
	RewriteRule ^(.*)$ http://yourdomain.com/$1 [P]
</IfModule>
 {%endcodeblock%}
 
 * 等待域名解析成功
 
 **提供个例子** <http://money.fanaifan.com>
 
 	如果在设置的时候,有什么问题,直接留言,我会在第一时间回复尽可能的帮助您!
 
 
