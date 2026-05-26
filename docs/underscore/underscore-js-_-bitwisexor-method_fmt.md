# 下划线.js _.bitwiseXor()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-bitwisexor-method/](https://www.geeksforgeeks.org/underscore-js-_-bitwisexor-method/)

`_.bitwiseXor()`方法返回对所有参数使用按位异或（`^`）运算符的结果。

## 语法

```
_.bitwiseXor(val1, val2, ..., valn);
```

## 参数

该方法取`n`个值对其进行运算。

## 返回值

此方法返回对所有参数使用按位`^`运算符的结果。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装下划线.js contrib 库。可以使用`npm install underscore-contrib-save`来安装下划线.js contrib 库。

## 例1

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bX = _.bitwiseXor(1, 3);

console.log("The bitwiseXor is :", bX);
```

**输出：**

```
The bitwiseXor is : 2
```

## 例2

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bX = _.bitwiseXor(1, 3, 5, 7);

console.log("The bitwiseXor is :", bX);
```

**输出：**

```
The bitwiseXor is : 0
```

## 例3

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bX = _.bitwiseXor(1);

console.log("The bitwiseXor is :", bX);
```

**输出：**

```
The bitwiseXor is : 1
```