---
title: Hexo发布文章流程
date: 2021-06-22 17:20:00
categories:
- 搭建博客
- hexo
tags:
- hexo
---
博客站点搭建好后，接下来就需要用文章使其变得充实。
<!--more-->

### 新建文章

在本地博客项目文件夹下打开gitbush，使用以下指令新建一篇新文章：

```
hexo new [layout] <title>
```

- [layout]为可选参数，用于指定文章类型，未填写则采用配置文件中default_layout决定。

- < title>为必填参数，用于指定文章的标题。

指令执行完后会在项目文件夹下的**source/_posts**生成对应文章标题的markdown文件。

### 编写文章

生成的文章为markdown格式，打开后有文章的抬头，接下去就可以用markdown格式编写文章了，这边就不展开说明。

### 发布文章

使用以下指令清理项目缓存文件：

```
hexo clean
```

使用以下指令发布文章：

```
hexo g -d
```

> 如果原本就有文章，只需要文章开头加入hexo特定格式，并放入_posts文件夹内，也可以进行上传。