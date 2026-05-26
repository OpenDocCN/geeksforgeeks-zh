# Underscore.js _.sub()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-sub-method/](https://www.geeksforgeeks.org/underscore-js-_-sub-method/)

`_.sub()`方法用于计算所有给定参数的差值。

**语法：**

```javascript
_.sub( val1, val2, ..., valn );
```

**参数：** 该方法接受 `n` 个值作为参数进行运算。

**返回值：** 此方法返回所有给定参数的差值。

**注意：** 这在普通的 JavaScript 中无法直接工作，因为它需要安装 `underscore-contrib` 库。可以使用 `npm install underscore-contrib` 命令来安装 `underscore.js` 的 contrib 库。

## 示例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var diff = _.sub( 10, 2, 4, 1 );

console.log("The Difference is : ", diff);
```

**输出：**

```
The Difference is :  3
```

## 示例 2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var diff = _.sub( 10 );

console.log("The Difference is : ", diff);
```

**输出：**

```
The Difference is :  10
```

## 示例 3

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var diff = _.sub( 1, 3, 5, 7, 9, 99, 100 );

console.log("The Difference is : ", diff);
```

**输出：**

```
The Difference is :  -222
```