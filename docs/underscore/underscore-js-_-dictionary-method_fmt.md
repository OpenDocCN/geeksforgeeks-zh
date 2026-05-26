# Underscore.js _.dictionary() 方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-dictionary-method/](https://www.geeksforgeeks.org/underscore-js-_-dictionary-method/)

`_.dictionary()` 方法返回一个函数，该函数将尝试查找给定的字段。

## 语法

```
funct = _.dictionary( object );
```

## 参数

*   `object`：此方法接受要搜索字段的对象。

## 返回值

该方法返回一个函数，该函数将尝试查找给定的字段。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore-contrib 库。可以使用 `npm install underscore-contrib` 来安装 Underscore-contrib 库。

## 示例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var ob = { gfg : "GeeksforGeeks" }
var gfgg = _.dictionary( ob );

console.log(gfgg("gfg"));
```

**输出：**

```
GeeksforGeeks
```

## 示例 2

如果这个函数没有找到任何字段，那么它将返回 `undefined`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var ob = { gfg : "GeeksforGeeks" }
var gfgg = _.dictionary( ob );

console.log(gfgg("geek"));
```

**输出：**

```
undefined
```