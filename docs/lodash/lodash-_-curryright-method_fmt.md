# Lodash _.curryRight() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-curryright-method/](https://www.geeksforgeeks.org/lodash-_-curryright-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

`_.curryRight()` 方法用于返回给定函数的 curryRight 版本，其中给定参数从右到左进行处理。

## 语法

```javascript
_.curryRight( fun )
```

## 参数

该方法采用如上所列的单个参数，讨论如下。

*   `fun`: 这是 curried 版本应该用到的功能。

## 返回值

该方法返回 curried 函数。

## 注意

这个方法在正常的 JavaScript 中不会工作，因为它需要安装 Lodash contrib 库。可以使用 `npm install lodash-contrib --save` 来安装 lodash-contrib 库。

## 例 1

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to curry
function div(a, b, c) {
    return a / b / c;
}

// Using the _.curryRight() method
var curried = _.curryRight(div);

console.log("Curried division is :",
    curried(3)(3)(99));
```

**输出:**

```plaintext
Curried division is : 11
```

## 例 2

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to curry
function div(a, b, c, d) {
    return a - b - c - d;
}

// Using the _.curryRight() method
var curried = _.curryRight(div);

console.log("Curried Subtraction is :",
    curried(2)(1)(6)(44));
```

**输出:**

```plaintext
Curried Subtraction is : 35
```

## 例 3

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to curry
function div(a, b, c) {
    return ("a=" + a + " and b=" + b +
            " and c=" + c);
}

// Using the _.curryRight() method
var curried = _.curryRight(div);

console.log(curried("a")("b")("c"));
```

**输出:**

```plaintext
a=c and b=b and c=a
```