# Underscore.js _.unsplatl() 方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-unsplatl-method/](https://www.geeksforgeeks.org/underscore-js-_-unsplatl-method/)

`_.unsplatl()` 方法将一个期望数组的函数作为其第一个参数，并返回一个函数，该函数的工作原理相同，但采用前导参数列表。它类似于 `unsplat()` 方法。它模仿了 ECMAScript 6 中的 rest 参数语法。

## 语法

```
_.unsplatl( function )
```

## 参数

*   `function`: 是把第一个自变量作为数组的原始函数。

## 返回值

这个方法返回一个函数。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 underscore-contrib 库。可以使用 `npm install underscore-contrib --save` 来安装 underscore-contrib 库。

## 示例 1

```javascript
// Defining underscore contrib variable
var _ = require("underscore-contrib");

// Function that takes array as the
// first parameter
function g(arr, val) {
  return val + " : " + arr;
}

// Using the unsplatl() method
var gfgFunc = _.unsplatl(g);

console.log(gfgFunc(1, 2, 3, 4, "A"));
```

**输出:**

```
A : 1,2,3,4
```

## 示例 2

```javascript
// Defining underscore contrib variable
var _ = require("underscore-contrib");

// Function that takes array as the
// first parameter
function g(arr) {
  return arr;
}

// Using the unsplatl() method
var gfgFunc = _.unsplatl(g);

console.log(gfgFunc(1, 2, 3, 4));
```

**输出:**

```
[ 1, 2, 3, 4 ]
```

## 示例 3

```javascript
// Defining underscore contrib variable
var _ = require("underscore-contrib");

// Function that takes array as the
// first parameter
function g(arr, val) {
  return arr.join(val);
}

// Using the unsplatl() method
var gfgFunc = _.unsplatl(g);

console.log(
  gfgFunc("GeeksforGeeks", 
  "Computer Science Portal for Geeks", " : ")
);
```

**输出:**

```
GeeksforGeeks : Computer Science Portal for Geeks
```