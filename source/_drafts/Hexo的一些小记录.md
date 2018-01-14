---
title: Hexo的一些小记录
date: 2018-01-07 22:34:03
tags:
    - 博客笔记
---

1. 如何让列表页只显示部分内容？
<!--more-->
## 1. 如何让列表页只显示部分内容？

在文章中间加入：
```
<!--more-->
```
即可，但要在有内容输入之后

## 2. 如何显示标签？
在文章开头加入：
```
---
title: Hexo的一些小记录.md
date: 2018-01-07 22:34:03
tags:
    - 博客修改记录1
---
```
即可

## 3. 预览草稿
```
hexo s -g --draft
```

## 4. 模板文件的修改

页面的加载实际上是`layout/layout.ejs`渲染出来的

`layout/layout.ejs`解读如下：

1. 代码如下：

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="chrome=1">
    <title>
      <%= title %>
    </title>
```
效果：
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="chrome=1">
    <title>
      whbing
    </title>
```
2. 几个加载文件的说明
```
    <%- partial('_partials/side-panel') %>
    <div class="content-wrapper">
        <div class="content-wrapper__inner entry">
            <%- body %>
            <%- partial('_partials/footer') %>
```
`<%- body %>指的是index.ejs中的内容`