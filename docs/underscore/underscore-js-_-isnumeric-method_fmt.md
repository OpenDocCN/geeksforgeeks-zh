# 下划线.js `_.isNumeric()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isnumeric-method/](https://www.geeksforgeeks.org/underscore-js-_-isnumeric-method/)

`_.isNumeric()`方法检查给定值是否为数值，并返回相应的布尔值。可以是包含数值、指数记数法的字符串，也可以是`Number`对象等。

**语法:**

```
_.isNumeric( value );
```

**参数:**

*   `value`: 要检查数值的给定值。

**返回值:** 该方法返回一个布尔值（如果给定值为数值，则返回`true`，否则返回`false`）。

**注意:** 这在正常的JavaScript中无法工作，因为它需要安装`underscore-contrib`库。`underscore-contrib`库可以使用`npm install underscore-contrib`安装。

### 示例 1

```
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Numeric : " 
    + _.isNumeric(10000)); 
```

**输出:**

```
The Value is Numeric : true
```

### 示例 2: 数组总是返回 false。

```
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Numeric : " 
    + _.isNumeric([1,10])); 
```

**输出:**

```
The Value is Numeric : false
```

### 示例 3

```
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Numeric : " 
    + _.isNumeric(2.333)); 
```

**输出:**

```
The Value is Numeric : true
```

### 示例 4: 包含数值的字符串将返回 true。

```
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 

// Checking
console.log("The Value is Numeric : " 
    + _.isNumeric("1000")); 
```

**输出:**

```
The Value is Numeric : true
```