---
layout: default
title: 你好，世界
---

<h2>{{ page.title }}</h2>

<p>我的第一篇文章</p>

<p>{{ page.date | date_to_string }}</p>

三、一个实例
下面，我举一个实例，演示如何在github上搭建blog，你可以跟着一步步做。为了便于理解，这个blog只有最基本的功能。
在搭建之前，你必须已经安装了git，并且有github账户。
第一步，创建项目。
在你的电脑上，建立一个目录，作为项目的主目录。我们假定，它的名称为jekyll_demo。
　　$ mkdir jekyll_demo
对该目录进行git初始化。
　　$ cd jekyll_demo
　　$ git init
然后，创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件。
　　$ git checkout --orphan gh-pages
以下所有动作，都在该分支下完成。
第二步，创建设置文件。
在项目根目录下，建立一个名为_config.yml的文本文件。它是jekyll的设置文件，我们在里面填入如下内容，其他设置都可以用默认选项，具体解释参见官方网页。
　　baseurl: /jekyll_demo
目录结构变成：
　　/jekyll_demo
　　　　|--　_config.yml
第三步，创建模板文件。
在项目根目录下，创建一个_layouts目录，用于存放模板文件。
　　$ mkdir _layouts
进入该目录，创建一个default.html文件，作为Blog的默认模板。并在该文件中填入以下内容。
　　<!DOCTYPE html>
　　<html>
　　<head>
　　　　<meta http-equiv="content-type" content="text/html; charset=utf-8" />
　　　　<title>{{ page.title }}</title>
　　</head>
　　<body>

　　　　{{ content }}

　　</body>
　　</html>
Jekyll使用Liquid模板语言，{{ page.title }}表示文章标题，{{ content }}表示文章内容，更多模板变量请参考官方文档。
目录结构变成：
　　/jekyll_demo
　　　　|--　_config.yml
　　　　|--　_layouts
　　　　|　　　|--　default.html
第四步，创建文章。