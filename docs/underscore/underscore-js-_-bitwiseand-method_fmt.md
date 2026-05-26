# _.bitwiseAnd()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-bitwiseand-method/](https://www.geeksforgeeks.org/underscore-js-_-bitwiseand-method/)

`_.bitwiseAnd()`方法对所有参数使用按位与（Bitwise &）运算符并返回结果。

## 语法

```
_.bitwiseAnd( val1, val2, ..., valn );
```

## 参数

该方法接受 n 个值对其进行运算。

## 返回值

这个方法对所有参数使用按位与（&）运算符并返回结果。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 `underscore-contrib` 库。可以使用 `npm install underscore-contrib` 来安装 `underscore-contrib` 库。

## 示例1

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bA = _.bitwiseAnd( 1, 3 );

console.log("The bitwiseAnd is :", bA);
```

**输出：**

```
The bitwiseAnd is : 1
```

## 示例2

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bA = _.bitwiseAnd( 1, 3, 4, 6 );

console.log("The bitwiseAnd is :", bA);
```

**输出：**

```
The bitwiseAnd is : 0
```

## 示例3

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bA = _.bitwiseAnd( 1 );

console.log("The bitwiseAnd is :", bA);
```

**输出：**

```
The bitwiseAnd is : 1
```