layout: post
title: ESLint配置技巧
date: 2017-03-04 23:23:44
tags:
categories: 工具
---
### 问题

在使用VS Code配置ESLint插件时，发现ESLint语法检查对node环境的一些常量支持的不太好。
如图所示

![](./error.png)

### 解决办法

这里需要用到ESLint的API：[Disabling Rules with Inline Comments](http://eslint.org/docs/user-guide/configuring.html#configuring-rules)
使用注释的方法，单独禁用某一行代码的语法检查
如图所示

![](./correct.png)