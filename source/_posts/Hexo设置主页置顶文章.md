---
title: Hexo设置主页置顶文章
date: 2021-06-22 19:30:00
categories:
- 搭建博客
- hexo
tags:
- hexo
---
按照操作来，就可以把想要的文章置顶！
<!--more-->

### 修改脚本代码

1、在项目文件夹下**node_modules\hexo-generator-index\lib**文件夹中，找到博客主页编译对应脚本文件**generator.js**并打开。

2、找到以下代码内容：

```
sort(posts.data, (a, b) => (b.sticky || 0) - (a.sticky || 0));
```

注释或者删除。

3、在2的位置上粘贴上以下代码：

```
posts.data = posts.data.sort(function(a, b) {
        if(a.top && b.top) { // 两篇文章top都有定义
            if(a.top == b.top) return b.date - a.date; // 若top值一样则按照文章日期降序排
            else return b.top - a.top; // 否则按照top值降序排
        }
        else if(a.top && !b.top) { // 以下是只有一篇文章top有定义，那么将有top的排在前面（这里用异或操作居然不行233）
            return -1;
        }
        else if(!a.top && b.top) {
            return 1;
        }
        else return b.date - a.date; // 都没定义按照文章日期降序排
    });
```

4、保存文件

### 设置文章顺序

在文章的文档头可以通过设置：

```
top: [num]
```

- [num]为数字，数字越大，文章排序越靠前

如果未设置top属性，则默认按照文章发布时间进行排序。

> 文章置顶标识可以通过tag标签设置