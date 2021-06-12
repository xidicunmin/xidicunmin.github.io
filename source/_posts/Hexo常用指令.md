---
title: Hexo常用指令
date: 2021-06-12 19:20:00
categories:
- 搭建博客
- hexo
tags:
- hexo
---
如果需要持续维护更新用Hexo创建好的博客网站，常见的Hexo指令是必须要了解熟悉的。
<!--more-->

### hexo init

命令用于初始化本地文件夹为网站的根目录

```
hexo init [folder]
```

- [folder]为本地文件夹的名称，如果未填写则默认为当前目录。

### hexo new

这个命令主要用于新建文章，可以简写为**hexo n**

```
hexo new [layout] <title>
```

- [layout]为可选参数，用于指定文章类型，未填写则采用配置文件中default_layout决定。
- < title>为必填参数，用于指定文章的标题。

### hexo generate

这个命令用于将hexo项目源码编译为静态文件，可以简写为**hexo g**

```
hexo generate
```

指令后缀：

- **-d**选项，用于编译完直接发布，等于顺序执行**hexo gnerate**以及**hexo deploy**。

### hexo server

这个命令用于启动本地服务器，正常用于预览博客页面，可以简写为**hexo s**

```
hexo server
```

指令后缀：

- **-p**选项，指定服务器端口默认为4000。
- **-i**选项，指定服务器ip，默认为0.0.0.0。
- **-s**选项，静态模式，仅提供public文件夹中文件并禁用文件监视。

### hexo deploy

这个命令用于部署网站，可以简写为hexo d

```
hexo deploy
```

指令后缀：

- **-g**选项，与**hexo g -d**作用一致，用于直接编译部署项目。

具体使用可以参照[搭建博客](https://xidicunmin.github.io/2021/05/31/GitHub%E6%90%AD%E9%85%8DHexo%E7%94%9F%E6%88%90%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/)一文。

### hexo clean

这个命令用于清理缓存文件，一般编译部署前会使用。

```
hexo clean
```