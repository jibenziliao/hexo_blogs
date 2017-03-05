layout: post
title: HTML5 全局contenteditable属性
date: 2017-03-04 15:40:39
tags: HTML5
categories: HTML5
---
### 问题

今天无聊在上网时，发现某网站中的多选框中会有光标闪烁。

第一反应是，这个不会是input吧，但input只支持文本，里面的UI元素怎么弄的？

### 解决方案

后来发现，多选框的div有一个属性：contenteditable

原来这个contenteditable属性是HTML5的新属性。

[contenteditable](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/contenteditable) 属性规定是否可编辑元素的内容。