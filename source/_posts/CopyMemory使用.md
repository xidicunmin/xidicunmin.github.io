---
title: CopyMemory使用
date: 2021-08-15 11:35:00
updated: 
categories:
- C#
tags:
- CopyMemory
---
首先需要导入win32API：

[DllImport("kernel32.dll")]

然后声明CopyMemory的方法：

public static extern void CopyMemory(byte[] Destination, byte[] add, int Length);
