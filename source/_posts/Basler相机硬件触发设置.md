---
title: Basler相机硬件触发设置
date: 2021-06-02 19:13:02
updated: 2021-06-03 20:20:00
categories:
- 工业相机
- Basler
tags:
- Basler
---
很多项目为了节省时序都应用上硬件触发，最近正好有项目涉及到这方面，正好借此机会记录一下。
<!--more-->

## 相机接线

由于是硬件触发，也就是io信号触发，所以是需要通过外部接线来触发相机进行拍照的。相机pin脚示意图如下：

![Basler面阵相机pin脚图.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Basler面阵相机pin脚图.png)

另外pin4为输出io，如果有需要的话可以通过软件设置什么时间点输出io。

供电接线示意图未下：

![Basler相机接线图.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Basler相机接线图.png)

![Basler相机接线图1.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Basler相机接线图1.png)

![Basler相机接线图2.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Basler相机接线图2.png)

![Basler相机接线图3.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.4/博客图片/Basler/Basler相机接线图3.png)

如图所示，如果使用12v作为外触发电压，需要串联1k电阻，如果使用24v电压，则需要串联2k电阻。如果未串联电阻，可能会出现触发异常的情况。

## 相机配置

打开Basler官方相机软件pylon，链接相机并修改为大师模式，示意图如下：

![Pylon打开相机.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Pylon打开相机.png)

务必要选择大师模式，这样能更改的相机权限更多。

需要更改的相机设置主要有两部分：

### 相机输入信号

![Pylon硬件触发输入信号设置.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Pylon硬件触发输入信号设置.png)

- Trigger Mode为触发模式，on为开启触发模式，off则是自由采集模式；
- Trigger Sourse为触发来源，硬触发选择Line1，也可以选择软触发选项；
- Trigger Activation为触发的信号模式，有上升沿下降沿可选；

按照图中所示设置就完成了相机硬件触发中输入信号的设置。

### 相机输出信号

这部分为可选项，是否需要设置看项目需求，具体设置位置如下：

![Pylon输出信号设置.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Pylon输出信号设置.png)

- Line Selector为信号线设置，输出线路选择Line2；
- Line Source为输出信号的时间，可以根据需求进行选择；
- Line Inverter为信号反置，勾选时输出信号反置；

## 保存配置

basler相机正常会留有几个用户设置可供切换，这些配置是存在相机自带的内存中，具体保存位置如下图：

![Pylon配置保存.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Pylon配置保存.png)

- User Set Selector为当前选中的用户配置；
- User Set Load为将当前选中用户配置载入到当前配置；
- User Set Save为将当前配置保存到选中的用户配置中；
- Default Startup Set为设置相机开始默认启用的配置；

需要注意的是保存过后可以再载入一下，确认配置是否正确保存到用户配置中。

## 取图测试

配置完成后可以通过软件进行取图测试，在确保相机正常连接的情况下，上方的操作栏如图：

![Pylon取图操作栏.png](https://cdn.jsdelivr.net/gh/xidicunmin/CDN@1.3/博客图片/Basler/Pylon取图操作栏.png)

1. 单次采集，点击过后会弹出取图窗口，当取完图像会自动关闭采集通道，不再接受触发；
2. 批量采集，点击过后会弹出取图窗口，取完图像过后不会关闭采集通道，可以持续接受触发，需要手动停止；
3. 停止采集通道，点击过后不再接收触发指令的触发；
4. 相机取图状态，显示取图的张数以及当前帧率，可以用于判断是否有取到图像；

测试相机的时候务必需要打开相机采集通道，否则无法触发相机。
