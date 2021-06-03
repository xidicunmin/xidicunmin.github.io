---
title: Hexo更换主题
date: 2021-06-01 22:47:31
categories:
- 搭建博客
- hexo
tags:
- hexo
photos: https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/MD壁纸.jpeg
---
初始主题说实话真是不大行，有必要更换一套主题，提升下整体逼格。
<!--more-->

### 寻找主题

寻找主题的途径有许多，使用常用搜索引擎搜索就能让你眼花缭乱

![搜索hexo主题.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/搜索hexo主题.png)

好在Hexo很人性化，提供官方的[主题网站](https://hexo.io/themes/)供我们选择。

![官方主题站点.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/官方主题站点.png)

站内主题数量还是比较客观的，网上教程大部分推荐的都是Next主题，但是像我有明确的目标，我想要的主题是MD风格的，那么就可以在搜索栏进行关键字搜索。

![md主题搜索结果.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/md主题搜索结果.png)

在搜索结果点击预览图可以直接进入主题的demo中查看，通过一番比较，最终我选择了Meadow这款主题，接下来的安装也以此主题为基础。

### 安装主题

在搜索页点击预览图下的文字就可以进入主题的github主页（可能需要科学上网）：

![主题github主页.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/主题github主页.png)

点击code查看主题链接并复制：

![主题git地址.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/主题git地址.png)

将主题clone到hexo项目文件夹下themes文件夹下，指令如下：

![下载主题.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/下载主题.png)

通过此条指令会在themes下自动生成meadow文件夹，并将主题内容clone到文件夹内：

![主题目录.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/主题目录.png)

这样主题算安装完成了。

### 使用主题

主题安装后通过简单配置就可以使用了。

打开项目根目录配置文件_config.yml，找到下图位置，并修改成主题文件夹的名称保存并关闭：

![使用主题.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/使用主题.png)

在根目录打开git bath，依次输入以下指令更新项目：

```
hexo clean
```

```
hexo generate
```

更新编译完成可以开启本地服务：

```
hexo s
```

或者直接部署到GitHub上：

```
hexo deploy
```

更换皮肤效果如下：

![主题展示.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.2/博客图片/Hexo更换主题/主题展示.png)

关于hexo个性化配置以及主题配置后续再进行讲解。
