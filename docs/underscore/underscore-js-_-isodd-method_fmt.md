# Underscore.js _.isOdd()方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isodd-method/](https://www.geeksforgeeks.org/underscore-js-_-isodd-method/)

`_.isOdd()`方法检查给定值是否为奇数，相应地返回一个布尔值。

**语法:**

```javascript
_.isOdd( value );
```

**参数:**

*   `value`: 要检查奇数的给定值。

**返回值:** 该方法返回一个`布尔值`（如果给定值为奇数，则返回`true`，否则返回`false`）。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 Underscore-contrib 库。Underscore-contrib 库可以使用命令 `npm install underscore-contrib` 安装。

**例 1:**

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Odd : " + _.isOdd(41));
```

**输出:**

```javascript
The Value is Odd : true
```

**例 2:**

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Odd : " + _.isOdd(42));
```

**输出:**

```javascript
The Value is Odd : false
```

**示例 3:** 对于值 `0`，此方法返回 `false`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Odd : " + _.isOdd(0));
```

**输出:**

```javascript
The Value is Odd : false
```

**例 4:** 对于非整数值，此方法返回 `false`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Odd : " + _.isOdd("GFG"));
```

**输出:**

```javascript
The Value is Odd : false
```