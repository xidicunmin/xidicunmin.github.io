---
title: GitHub搭配Hexo生成个人博客
date: 2021-05-31 09:42:19
top: 1
categories:
- 搭建博客
- hexo
tags:
- hexo
- 置顶
photos: https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/本地主页.png
---
通过GitHub和Hexo来搭建自己的第一个博客吧！
<!--more-->
## **准备工作**

### github账号

### git环境

### node.js环境

## **新建博客仓库**

### 登录GitHub账号

### 新建GitHub仓库

仓库名称格式为**“账号名称”+.github.io**，如下图所示：

![newRepository.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/新建仓库.png)

![repositoryContext.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/仓库信息.png)

如果新建仓库时有勾选Add a README file，那么直接通过浏览器访问[xidicunmin.github.io](https://xidicunmin.github.io)可以直接访问个人主页，显示的是REAADME内的信息。

## **安装**

### 安装hexo

在希望生成hexo项目的目录下右击，选择git bash进入git命令行。输入下面指令进行安装：

```
npm install hexo -g
```

安装完毕后可以输入下面指令确保hexo已安装：

```
hexo -v
```

出现下图信息说明hexo已经成功安装：

![hexo-v.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/hexo版本信息.png)

### 初始化项目

使用以下命令新建一个项目：

```
hexo init hexotest
```

![hexoinit.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/初始化项目.png)

hexotest可替换为任意项目名称，此次为范例。

成功后目录下会出现该项目文件夹：

![projectName.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/项目文件夹名称.png)

### 编译项目

进入项目文件夹内打开git命令行，或者也可以在当前命令行窗口输入下面指令直接进入项目文件夹内：

```
cd hexotest
```

确保当前命令行为项目文件夹内后，输入下面命令进行编译：

```
hexo generate
```

### 本地运行

输入以下指令，可以开启本地服务：

```
hexo s
```

![hexos.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/开启本地服务.png)

（注意：复制访问地址时采用ctrl+c会导致本地服务结束)

在浏览器输入访问[地址](https://localhost:4000)，便可以打开项目默认主页：

![localPage.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/本地主页.png)

## **部署**

### 修改配置文件

hexo项目的配置文件为项目根目录下的_config.yml，项目的基本配置主要存放在这个文件中，可以用notepad或者记事本打开：

![config.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.1/博客图片/GitHub搭配Hexo生成个人博客/配置文件名称.png)

这次主要修改的部分是部署相关，目的是部署到github上。可以从配置文件中找寻到以下配置信息：

```
# Deployment
## Docs: https://hexo.io/docs/one-command-deployment
deploy:
  type: ''
```

根据前面设置好的GitHub仓库地址以及分支名称，按照以下格式进行增改，主要替换地址即可：

```
# Deployment
## Docs: https://hexo.io/docs/one-command-deployment
deploy:
  type: git
  repo: git@github.com:xidicunmin/xidicunmin.github.io.git
  branch: main
```

需要注意格式问题，分支名称最好直接是仓库主分支。

### 安装部署插件

使用部署命令前，需要先执行下面指令安装部署插件：

```
名称npm install hexo-deployer-git --save
```

如果未安装部署插件，可能会出现以下提示：

```
Deployer not found: git
```

### 执行部署命令

使用下面指令就可以把本地项目部署到github上：

```
hexo deploy
```

部署完，在GitHub仓库里可以看到和本地项目一样的内容。

## **访问**

部署完成后，这是再次访问GitHub主页[xidicunmin.github.io](https://xidicunmin.github.io)出现的就不是README内容，而是hexo主页。
