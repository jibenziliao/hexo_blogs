title: React-Native-Bugs
date: 2016-04-06 22:54:13
tags: [React,React-Native]
---
#### input标签没有onChange事件时，React会在控制台报出很详细的错误：
###### React provides very detailed errors in the console. For instance, rendering ``<input>`` without onChange gives : 

```
Warning: You provided a value prop to a form field 
without an onChange handler. This will render a 
read-only field. If the field should be mutable use
defaultValue. Otherwise, set either onChange or 
readOnly. Check the render method of MyComponent

```

[相关链接:][url]
[url]: http://ctheu.com/2015/02/05/how-do-you-react/