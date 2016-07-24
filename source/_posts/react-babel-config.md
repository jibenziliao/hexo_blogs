title: JSX解析器：babel-preset-react
date: 2016-04-05 22:14:14
tags: [Babel,JSX,React,React-Native]
---
#### 安装Babel命令行工具：
``` 
npm install --global babel-cli
npm install babel-preset-react
```

#### 使用Babel离线解析JSX：


``` 
babel --presets react src --watch --out-dir build
```

<!--more-->
> 
__说明:__ 

>jsx语法的文件在src目录，目标目录为build目录;修改了含有jsx语法的js文件后，babel可以实时监听并更新页面。



