# 下划线.js `_.isDecreasing()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isdecreasing-method/](https://www.geeksforgeeks.org/underscore-js-_-isdecreasing-method/)

`_.isDecreasing()`方法检查参数是否是单调递减的值，或者每个参数是否小于前一个参数。

## 语法

```
_.isDecreasing(val1, val2, ..., valn);
```

## 参数

该方法检查 n 个值的递减顺序。

## 返回值

该方法返回一个布尔值（如果给定值在减少，则返回`true`，否则返回`false`）。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装`underscore.js-contrib`库。

可以使用`npm install underscore-contrib --save`来安装`underscore.js-contrib`库。

## 示例 1

方法返回`true`。

### Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');
// Checking
console.log("The Value is Decreasing : " + _.isDecreasing(3, 2, 1));
```

**输出:**

```
The Value is Decreasing : true
```

## 示例 2

方法返回`false`。

### Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');
// Checking
console.log("The Value is Decreasing : " + _.isDecreasing(3, 2, 1, 2));
```

**输出:**

```
The Value is Decreasing : false
```