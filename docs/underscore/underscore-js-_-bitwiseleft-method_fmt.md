# 下划线.js _.bitwiseLeft()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-bitwiseleft-method/](https://www.geeksforgeeks.org/underscore-js-_-bitwiseleft-method/)

`_.bitwiseLeft()`方法对所有参数使用`<<`运算符并返回结果。

## 语法

```
_.bitwiseLeft(val1, val2,..., valn);
```

## 参数

该方法接受`n`个值作为参数。

## 返回值

这个方法返回在参数上使用`<<`运算符的结果。

## 注意

这在正常的JavaScript中无法工作，因为它需要安装`underscore-contrib`库。可以使用`npm install underscore-contrib`来安装`underscore-contrib`库。

## 例1

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bL = _.bitwiseLeft( 1, 3 );

console.log("The bitwiseLeft is :", bL);
```

**输出：**

```
The bitwiseLeft is : 8
```

## 例2

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bL = _.bitwiseLeft( 1, 3, 2 );

console.log("The bitwiseLeft is :", bL);
```

**输出：**

```
The bitwiseLeft is : 32
```

## 例3

### JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bL = _.bitwiseLeft( 1 );

console.log("The bitwiseLeft is :", bL);
```

**输出：**

```
The bitwiseLeft is : 1
```