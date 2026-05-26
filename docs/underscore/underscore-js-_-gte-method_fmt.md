# Underscore.js _.gte()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-gte-method/](https://www.geeksforgeeks.org/underscore-js-_-gte-method/)

`_.gte()` 方法检查每个参数是否大于或等于它的下一个参数。

**语法:**

```
_.gte( val1, val2,..., valn );
```

**参数:** 该方法取 n 个值对其进行运算。

**返回值:** 这个方法返回一个布尔值。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。

可以使用 `npm install underscore-contrib --save` 来安装 Underscore.js contrib 库。

**例 1:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var greater = _.gte(4, 1, 1);

console.log("Each argument is greater than or"+
            " equal to its next argument :",greater);
```

**输出:**

```
Each argument is greater than or equal to 
its next argument : true
```

**例 2:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var greater = _.gte(4, 3, 2, 1);

console.log("Each argument is greater than or"+
            " equal to its next argument :",greater);
```

**输出:**

```
Each argument is greater than or equal to 
its next argument : true
```

**例 3:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var greater = _.gte(4, 3, 2, 1, 44);

console.log("Each argument is greater than or"+
            " equal to its next argument :",greater);
```

**输出:**

```
Each argument is greater than or equal 
to its next argument : false
```