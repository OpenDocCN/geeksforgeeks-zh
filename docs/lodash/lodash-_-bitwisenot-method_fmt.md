# Lodash _.bitwiseNot() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-bitwisenot-method/](https://www.geeksforgeeks.org/lodash-_-bitwisenot-method/)

**Lodash** 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.bitwiseNot()` 方法用于返回对给定参数使用按位非运算符 (`~`) 的结果。

**语法:**

```javascript
_.bitwiseNot( value );
```

**参数:** 该方法采用单个值作为参数，描述如下:

*   `value`: 是应用按位非运算符 (`~`) 的值。

**返回值:** 此方法返回对参数使用按位非运算符 (`~`) 的结果。

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib --save` 命令安装。

**例 1:**

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseNot() method
var bN = _.bitwiseNot( 1 );

console.log("The bitwiseNot is :", bN);
```

**输出:**

```
The bitwiseNot is : -2
```

**例 2:**

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseNot() method
var bN = _.bitwiseNot( 10 );

console.log("The bitwiseNot is :", bN);
```

**输出:**

```
The bitwiseNot is : -11
```

**例 3:**

```javascript
// Adding lodash-contrib library
var _ = require('lodash-contrib');

// Using the _.bitwiseNot() method
var bN = _.bitwiseNot( 100 );

console.log("The bitwiseNot is :", bN);
```

**输出:**

```
The bitwiseNot is : -101
```