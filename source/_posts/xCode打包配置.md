title: xCode打包配置
date: 2016-02-16 20:27:34
tags: [xCode,cordova,ionic]
---
#### 选择企业证书：

#### build settings:
1.如果打包后APP不能访问远程服务器，则添加以下属性
> 原因其实这是苹果加大安全的管控，将以往HTTP协议强制改为HTTPS协议

```bash
NSAppTransportSecurity 类型 Dictionary Dictionary
添加 NSAllowsArbitraryLoads 类型 Boolean ,值设为 YES
```
<!--more-->
2.提示Undefined symbols for architecture arm64等错误.

```bash
Build Settings 选项
搜索 dead, Dead Code Stripping(去除死代码选项)
改为No
```
3.Xcoede provisioning prifles需要手动删除

```bash
com+shift+g，输入以下路径
~/Library/MobileDevice/Provisioning Profiles
```
4.一些第三方依赖库或sdk不支持bitcode，所以要讲bitcode设置为no

```bash
bitcode
```

