layout: post
title: JavaScript词法作用域
date: 2017-03-14 11:16:31
tags:
categories: JavaScript
---

看到一道经典的面试题，关于JavaScript作用域问题。

# JavaScript变量作用域 #

## 函数限定变量作用域 ##

在JavaScript中，只有函数可以限定一个变量的作用范围。
```JavaScript
if(true) {
 var num = 10;
}
console.log(num);

```
上面的代码会输出10.

```JavaScript
var func = function() {
 var num = 10;
};
try {
 console.log(num);
} catch(e) {
 console.log(e);
}
```
上面的代码运行时，会抛出一个异常，__ReferenceError: num is not defined__，即变量num没有定义。
也就是说，函数内的变量无法在函数外使用。但是可以在函数内部使用，即使是在赋值之前，如下：
```JavaScript
var func = function() {
 console.log(num);
 var num = 10;
 console.log(num);
};
try {
 func();
} catch(e) {
 console.log(e);
}
```
这里会先在控制台先打后印undefined和10。
这里会出现undefined牵扯到子域访问父域的问题。

## 子域访问父域 ##

在JavaScript中，只有函数可以限定变量的作用域，那么在函数中的函数就成为该作用域的子域。
子域中的代码可以访问到父域中的变量，如下：
```JavaScript
var func = function() {
 var num = 10;
 var sub_func = function() {
  console.log(num);
 };
 sub_func();
};
func();
```
执行得到结果10。可以看到上文所说的变量访问情况。但是在子域中访问父域的代码也是有条件的。如下面代码：
```JavaScript
var func = function() {
 var num = 10;
 var sub_func = function() {
  var num = 20;
  console(num);
 };
 sub_func();
};
func();
```
子域中又定义了一个变量`var num=20`,那么子域会访问当前子域中的变量，不会在访问父域中的变量。

由此可见访问有一定规则可言。 在JavaScript中使用变量，JavaScript解释器首先在当前作
用域中搜索是否有该变量的定义，如果有，就是用这个变量；如果没有就到父域中寻找该变量。

以此类推，直到最顶级作用域，仍然没有找到就抛出异常"变量未定义"。看下面代码：
```JavaScript
(function() {
 var num = 10;
 (function() {
  var num = 20;
  (function(){
   console.log(num);
  })()
 })();
})();
```
这段代码执行后打印出20。如果将`var num = 20;`去掉，那么打印的就是10。 同样，如果再去掉
`var num = 10`，那么就会出现未定义的错误。

## 链接 ##

其它更详细的解释及案例：

[JavaScript 开发进阶：理解 JavaScript 作用域和作用域链](http://www.cnblogs.com/lhb25/archive/2011/09/06/javascript-scope-chain.html)

[深入理解JavaScript高级之词法作用域和作用域链](http://www.jb51.net/article/44307.htm)




