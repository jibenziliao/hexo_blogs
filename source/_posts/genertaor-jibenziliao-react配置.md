layout: post
title: genertaor-jibenziliao-react配置
date: 2017-03-09 22:49:30
tags:
categories: webpack
---

为了方便今后的项目搭建，开始学习搭建自己的[yeoman](http://yeoman.io/generators/)脚手架

# genertaor-jibenziliao-react #

## 说明 ##

npm仓库地址：[genertaor-jibenziliao-react](https://www.npmjs.com/package/generator-jibenziliao-react)

github仓库地址：[genertaor-jibenziliao-react](https://github.com/jibenziliao/generator-jibenziliao-react)

介绍页面：[genertaor-jibenziliao-react](https://jibenziliao.github.io/generator-jibenziliao-react/)

### 搭建步骤 ###

搭建步骤网上有很多，这里简单说明一下

项目名称一定要以`generator-*`开头，不然到时候yeoman找不到你的这个脚手架。

新建目录`genertaor-jibenziliao-react`，执行`npm init`，创建一个package.json

```
{
  "name": "generator-jibenziliao-react",
  "version": "0.0.7",
  "description": "基于react+webpack2的项目脚手架",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/jibenziliao/generator-jibenziliao-react.git"
  },
  "keywords": [
    "yeoman-generator",
    "react",
    "webpack",
    "yeoman"
  ],
  "author": "jibenziliao",
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/jibenziliao/generator-jibenziliao-react/issues"
  },
  "homepage": "https://jibenziliao.github.io/generator-jibenziliao-react/",
  "dependencies": {
    "lodash": "^4.17.4",
    "yeoman-generator": "^1.1.1",
    "date-util": "^1.2.1"
  }
}
```

package.json中的`description`字段也是必写的，这是yeoman索引出来项目的简介。

关键词里必须包含`yeoman-generator`,这样yeoman才能对项目建立索引。

在根目录下新建一个目录`generators`，最后使用`yo`初始化的项目的时候，所有的资源文件都是从这个目录下拷贝的。
官方还支持另一种目录结构，这里就不做介绍了。感兴趣的可以前往[yeoman官网](http://yeoman.io/authoring/index.html)查看完整教程。

package.json中的`dependencies`必须要有`yeoman-generator`。

项目的模板文件在`generators/app/templates/`目录下。

`yeoman`脚手架有个生成周期的概念：

> 当执行yo example启动生成器时，它会沿着它的生命周期执行如下特定名称的函数，这些特定名称的函数会放进一个队列里面按顺序执行，如果功能函数不是特定的函数名称，则放进另一个队列default按顺序执行。这些特定的函数名称有:

     initializing : 初始化阶段
    - prompting : 接受用户输入阶段
    - configuring : 保存配置信息和文件，如.editorconfig
    - default : 非特定的功能函数名称，本项目并没有用到
    - writing : 生成项目目录结构阶段（从templates目录下拷贝文件到项目中，需要注意配置路径）
    - conflicts : 统一处理冲突，如要生成的文件已经存在是否覆盖等处理
    - install : 安装依赖阶段，如通过npm、bower
    - end : 生成器即将结束

具体的配置可查看源码
