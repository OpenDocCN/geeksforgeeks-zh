# Underscore.js _.unsplat()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-unsplat-method/](https://www.geeksforgeeks.org/underscore-js-_-unsplat-method/)

`_.unsplat()`方法将一个需要数组的函数作为其最后一个参数，并返回一个工作方式相同的函数，但使用一个尾随参数列表代替一个数组。

## 语法

```
_.unsplat( function );
```

## 参数

*   **function**: 将最后一个参数作为数组的原始函数。

## 返回值

这个方法返回一个函数。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。

可以使用 `npm install underscore-contrib` 来安装 Underscore.js contrib 库。

## 示例

### 例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function g (val, arr) {
    return val + " : " + arr;
}

var gfgFunc = _.unsplat(g);

console.log(gfgFunc("a", 1, 2, 3, 4))
```

**输出:**

```
a : 1, 2, 3, 4
```

### 例 2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function g (arr) {
    return arr;
}

var gfgFunc = _.unsplat(g);

console.log(gfgFunc(1, 2, 3, 4))
```

**输出:**

```
[ 1, 2, 3, 4 ]
```

### 例 3

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function g (val, arr) {
    return arr.join(val);
}

var gfgFunc = _.unsplat(g);

console.log(gfgFunc(" : ", "GeeksforGeeks", 
      "Computer Science Portal for Geeks"))
```

**输出:**

```
GeeksforGeeks : Computer Science Portal for Geeks
```