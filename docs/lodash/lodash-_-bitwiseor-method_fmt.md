# Lodash _.bitwiseOr() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-bitwiseor-method/](https://www.geeksforgeeks.org/lodash-_-bitwiseor-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.bitwiseOr()` 方法用于返回对所有给定参数使用按位或运算符 (`|`) 的结果。

**语法:**

```javascript
_.bitwiseOr( val1, val2, ..., valn );
```

**参数:** 该方法采用可变数量的参数，并对其进行按位或运算。

**返回值:** 该方法返回对所有参数使用按位或运算符的结果。

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash.js contrib` 库。可以使用 `npm install lodash-contrib --save` 命令来安装。

**例 1:**

### JavaScript 描述语言

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Using the _.bitwiseOr() method
var bO = _.bitwiseOr( 1, 2, 3, 4, 5 );

console.log("The bitwiseOr is :", bO);
```

**输出:**

```
The bitwiseOr is : 7
```

**例 2:**

### JavaScript 描述语言

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Using the _.bitwiseOr() method
var bO = _.bitwiseOr( 1, 2, 1, 3, 3, 4, 7, 8, 5 );

console.log("The bitwiseOr is :", bO);
```

**输出:**

```
The bitwiseOr is : 15
```

**例 3:**

### JavaScript 描述语言

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

// Using the _.bitwiseOr() method
var bO = _.bitwiseOr( 5 );

console.log("The bitwiseOr is :", bO);
```

**输出:**

```
The bitwiseOr is : 5
```