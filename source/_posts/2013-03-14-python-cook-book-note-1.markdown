---
layout: post
title: "python cookbook 笔记 1"
date: 2013-03-14 11:27
comments: true
categories: 

---

## 每次处理一个字符

{%codeblock lang:python%}
import sets
magic_chars = sets.Set('abrddd')
poppins_chars = sets.Set('bdccc')
print ''.join(magic_chars & poppins_chars) #集合的交集
# ==> bd
{%endcodeblock%}

## 字符和字符值之间的转换

{%codeblock lang:python%}
print ord('a')  # ==> 97
print chr(97)   # ==> a
print ord(u'\u2020')  # ==> 8224
print repr(unichr(8224))  # ==> u'\u2020'
print repr(chr(97))  # ==> 'a'
print repr(str(97))  # ==> '97'
{%endcodeblock%}

	repr() 用来取得对象的规范字符串表示
	chr() 将一个小整数作为参数并返回对应于ASCII单字符的字符串
	str() 以任何整数为参数,返回一个该整数的文本形式的字符串

**把一个字符串转化为一个包含各个字符的值的列表**
	
{%codeblock lang:python%}
print map(ord, 'ciao') # ==> [99, 105, 97, 111]
{%endcodeblock%}

**通过一个包含了字符值的列表创建字符串**

{%codeblock lang:python%}
print ''.join(map(chr, range(97,100))) # ==> abc
{%endcodeblock%}


## 测试一个对象是否是类字符串

> 获得事后原谅总是比事先得到许可要容易得多(It's easier to ask forgiveness than permission) 简称:EAFP
