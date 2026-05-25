# Lodash _.mod()方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-mod-method/](https://www.geeksforgeeks.org/lodash-_-mod-method/)

`Lodash`是一个工作在下划线之上的JavaScript库。

`_.mod()`方法用于返回给定数的模，即给定被除数除以给定除数的余数。

## 语法

```
_.mod( dividend, divisor )
```

## 参数

该方法取两个参数，如上所述，描述如下：

*   `被除数`：是计算模数的被除数。
*   `除数`：是用来计算模数的除数。

## 返回值

该方法从给定的参数返回计算的模数。

## 注意

这在正常的JavaScript中不会起作用，因为它需要安装lodash contrib库。可以使用`npm install lodash-contrib --save`来安装Lodash contrib库。

## 例1：JavaScript描述语言

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Using the _.mod() method
var mod = _.mod( 33, 5 );

console.log("The Modulus is :", mod);
```

**输出：**

```
The Modulus is : 3
```

## 例2：JavaScript描述语言

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Using the _.mod() method
var mod = _.mod( 170, 35 );

console.log("The Modulus is :", mod);
```

**输出：**

```
The Modulus is : 30
```

## 例3：JavaScript描述语言

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Using the _.mod() method
var mod = _.mod( 12, 1 );

console.log("The Modulus is :", mod);
```

**输出：**

```
The Modulus is : 0
```