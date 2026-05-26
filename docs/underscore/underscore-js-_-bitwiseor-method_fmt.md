# 下划线.js `_.bitwiseOr()`方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-bitwiseor-method/](https://www.geeksforgeeks.org/underscore-js-_-bitwiseor-method/)

`_.bitwiseOr()`方法返回对所有参数使用按位或（`|`）运算符的结果。

**语法：**
```
_.bitwiseOr(val1, val2, ..., valn);
```

**参数：** 该方法取`n`个值对其进行运算。

**返回值：** 这个方法返回对所有参数使用按位或运算符的结果。

**注意：** 这在正常的JavaScript中无法工作，因为它需要安装`underscore.js contrib`库。可以使用`npm install underscore-contrib-save`来安装`underscore.js contrib`库。

**例1：**

## JavaScript
```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bO = _.bitwiseOr( 1, 3 );

console.log("The bitwiseOr is :", bO);
```

**输出：**
```
The bitwiseOr is : 3
```

**例2：**

## JavaScript
```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bO = _.bitwiseOr( 1, 3, 4, 6 );

console.log("The bitwiseOr is :", bO);
```

**输出：**
```
The bitwiseOr is : 7
```

**例3：**

## JavaScript
```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bO = _.bitwiseOr( 3 );

console.log("The bitwiseOr is :", bO);
```

**输出：**
```
The bitwiseOr is : 3
```