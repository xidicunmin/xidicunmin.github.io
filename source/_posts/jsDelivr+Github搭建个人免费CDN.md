---
title: jsDelivr+Github搭建个人免费CDN
date: 2021-08-15 12:00:00
categories:
- 搭建博客
tags:
- jsDelivr
- CDN
photos: https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/title.png
---
CDN的全称是Content Delivery Network，中文翻译过来为内容分发网络。主要原理是依靠部署在各地的服务器，通过中心平台的调度，使得用户能够就近获取所需内容，降低网络拥堵，提高访问速度。详情可以自行搜索。

通过jsDelivr提供的CDN服务，我们可以在网络上快速访问Github上托管的内容。那么也就说明我们可以在GitHub上建个仓库，用于存放类似于博客图片之内的内容，再通过jsDelivr进行获取，提高博客整体加载速度，那么接下来看看具体怎么实现。

<!--more-->

### 新建CDN仓库

首先需要新建一个仓库用来存放资源，至于叫什么名称都是可以。

![新建仓库.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/新建仓库.png)

### 克隆仓库到本地

通过**git clone**指令把CDN仓库克隆到本地。

![下拉本地.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/下拉本地.png)

![下拉指令.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/下拉指令.png)

### 上传资源

把资源放入仓库并上传到GitHub。

![提交本地资源指令.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/提交本地资源指令.png)

### 发布仓库

在GitHub仓库主页上进行Release版本发布。

![点击tag.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/点击tag.png)

![创建releases版本.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/创建releases版本.png)

![releases版本信息.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN/博客图片/jsDelivr+Github免费创建图片资源库/releases版本信息.png)

### 访问资源

通过jsDelivr提供的方式可以直接访问仓库内的资源，方式如下：

```
https://cdn.jsdelivr.net/gh/[用户名]/[仓库名称]@[发布版本号]/[文件路径]
```

- [用户名]为必填项，内容为GitHub用户名；
- [仓库名称]为必填项，内容为GitHub资源仓库名称；
- [发布版本号]为可选项，内容为Release版本号，未填写时（**前部无@**）访问的是最新的资源，填写时（**前部有@**）访问设置版本的资源；
- [文件路径]为必填项，内容为访问文件对应路径；
