# 下划线.js _.add()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-add-method/](https://www.geeksforgeeks.org/underscore-js-_-add-method/)

`_.add()`方法返回所有给定参数的总和。

**语法:**
```
_.add(val1, val2,..., valn);
```

**参数:** 该方法接受`n`个值进行运算。

**返回值:** 这个方法返回所有给定参数的总和。

**注意:** 这在正常的JavaScript中无法工作，因为它需要安装`underscore-contrib`库。可以使用`npm install underscore-contrib`来安装`underscore-contrib`库。

**例1:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var sum = _.add( 1, 2, 4, 1 );

console.log("The Sum is : ", sum);
```

**输出:**
```
The Sum is : 8
```

**例2:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var sum = _.add( 1 );

console.log("The Sum is : ", sum);
```

**输出:**
```
The Sum is : 1
```

**例3:**

## JavaScript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var sum = _.add( 1, 3, 5, 7, 9, 99, 100 );

console.log("The Sum is : ", sum);
```

**输出:**
```
The Sum is : 224
```