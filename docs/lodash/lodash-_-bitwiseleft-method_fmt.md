# Lodash _.bitwiseLeft() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-bitwiseleft-method/](https://www.geeksforgeeks.org/lodash-_-bitwiseleft-method/)

**Lodash** 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.bitwiseLeft()` 方法用于返回对所有给定参数使用按位左运算符 (`<<`) 的结果。

**语法:**

```javascript
_.bitwiseLeft( val1, val2,..., valn )
```

**参数:** 该方法采用可变数量的参数，并对其进行按位左操作。

**返回值:** 该方法返回对所有参数使用按位左运算符的结果。

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib` 来安装。

## 示例 1

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseLeft() method
var bL = _.bitwiseLeft( 1, 3, 5, 7, 9 );

console.log("The bitwiseLeft is :", bL);
```

**输出:**

```
The bitwiseLeft is : 16777216
```

## 示例 2

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseLeft() method
var bL = _.bitwiseLeft( 1, 3, 2 );

console.log("The bitwiseLeft is :", bL);
```

**输出:**

```
The bitwiseLeft is : 32
```

## 示例 3

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseLeft() method
var bL = _.bitwiseLeft( 1 );

console.log("The bitwiseLeft is :", bL);
```

**输出:**

```
The bitwiseLeft is : 1
```