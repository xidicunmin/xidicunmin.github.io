---
title: Pylon软件安装以及连接相机
date: 2021-06-03 20:02:30
categories:
- 工业相机
- Basler
tags:
- Basler
---
## 安装软件

双击打开pylon安装包，按照下图顺序进行安装：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Pylon5安装步骤1.png)

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Pylon5安装步骤2.png)

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Pylon5安装步骤3.png)

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Pylon5安装步骤4.png)

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Pylon5安装步骤5.png)

点击instal，等待软件安装完成。

## 连接相机

### GigE类型

双击桌面中pylon IP Configurator图标进入相机配置界面：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/gige相机配置软件界面.png)

1. 为相机显示窗口，会自动罗列目前检测的相机，并标注当前相机的状态；
2. 配置相机ip的位置，正常采用static IP配置，也就是静态ip设置，将相机与网口的网段设置一致，点击保存就可以连接上相机；

如果桌面并没有该软件图标，可以到软件安装目录下去启动：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/gige相机配置软件目录.png)

### CameraLink类型

进入pylon软件安装根目录，将CL相机配置软件发送到桌面快捷方式：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/cl相机配置软件目录.png)

打开ClConfigurator软件，勾选上所有端口进行相机搜索：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/cl相机配置软件找寻相机.png)

搜索到相机后添加保存，如果没有搜索到相机，请检查相机接线和软件是否安装到位，有很大可能是两根CameraLink线接反了：

![截图](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/cl相机配置软件相机结果.png)