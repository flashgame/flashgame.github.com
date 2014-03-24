---
author: wang
comments: true
layout: post
title: 测试博客系统
tags:["测试","博客，人家"]
	-tags,tags2
	-tags3
	-tags4
---
# 测试博客系统
博客的文章是由以下部分组成的：

* 元数据标签
* 文章内容

文章内容就是纯markdown语法编写的，学一下语法就好了。在这里主要测试的，还是`元数据标签`。标签的代码内容如下：

    ---
    author: ****
    comments: true
    date: 2014-03-22 16:34:03
    layout: post
    title: 测试博客系统
    ---

上面标签的含义应该是这样的：

* author：作者
* comments：是否能够评论。评论是使用disqus插件实现的。
* date:文章生成的时间，将会显示在文章列表页中
* layout：文章的位置
* title：文章的标题

有些博客的无数据标签是这样的：

    ---
    layout: post
    title: "Python的逻辑运算"
    tagline: "Logic Operation In Python"
    description: "Python中的逻辑运算的规定以及实质"
    tags: ["Python", "语义"]
    ---
多了`tagline`，`description`，`tags`标签，没有了`date`，`comments`标签。

`tagline`，`description`标签就先忽略，现在要测试两种情况：

* 没有`date`标签
* 添加`tag`标签内容

`tag`标签还有两种情况：

    情况1：
    /*使用方括号`[]`显示标签，每个标签使用双引号，使用逗号分隔；*/
    tags: ["Python", "语义"]

    情况2：
    /*使用`-`分隔，不两只的标签，使用换行*/
    tags:
    - Maven
    - Spring
    - Profile

最终的测试结果如下：



    


