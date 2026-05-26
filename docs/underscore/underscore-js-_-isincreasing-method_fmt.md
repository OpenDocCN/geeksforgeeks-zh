# Underscore.js _.isIncreasing() 方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-isincreasing-method/](https://www.geeksforgeeks.org/underscore-js-_-isincreasing-method/)

`_.isIncreasing()` 方法检查给定值是否单调递增或者每个参数是否大于前一个参数。

**语法：**

```
_.isIncreasing(val1, val2, ..., valn);
```

**参数：** 在该方法中，要检查 `n` 个值的递增顺序。

**返回值：** 该方法返回一个 `布尔值`（如果给定值为递增，则返回 `true`，否则返回 `false`）。

**注意：** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore.js contrib 库。Underscore.js contrib 库可以使用 `npm install underscore-contrib` 安装。

**例 1：** 此方法返回 `true`。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Checking
console.log("The Value is Increasing : "
    + _.isIncreasing(1, 2, 3, 4));
```

**输出：**

```
The Value is Increasing : true
```

**例 2：** 此方法返回 `false`。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Checking
console.log("The Value is Increasing : "
    + _.isIncreasing(3, 2, 1, 2));
```

**输出：**

```
The Value is Increasing : false
```

**示例 3：** 对于递增顺序的字符串值，此方法返回 `true`。

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Checking
console.log("The Value is Increasing : "
    + _.isIncreasing('a', 'b'));
```

**输出：**

```
The Value is Increasing : true
```