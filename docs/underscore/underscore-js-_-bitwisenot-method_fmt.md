# `_.bitwiseNot()`方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-bitwisenot-method/](https://www.geeksforgeeks.org/underscore-js-_-bitwisenot-method/)

`_.bitwiseNot()`方法返回在参数上使用`~`运算符的结果。

**语法：**
```javascript
_.bitwiseNot( value );
```

**参数：** 该方法取值对其进行`~`运算符运算。

**返回值：** 这个方法返回在参数上使用`~`运算符的结果。

**注意：** 这在正常的JavaScript中无法工作，因为它需要安装`underscore.js contrib`库。可以使用`npm install underscore-contrib`来安装`underscore.js contrib`库。

**例1：**
```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bN = _.bitwiseNot( 1 );

console.log("The bitwiseNot is :", bN);
```

**输出：**
```
The bitwiseNot is : -2
```

**例2：**
```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bN = _.bitwiseNot( 10 );

console.log("The bitwiseNot is :", bN);
```

**输出：**
```
The bitwiseNot is : -11
```

**例3：**
```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bN = _.bitwiseNot( 100 );

console.log("The bitwiseNot is :", bN);
```

**输出：**
```
The bitwiseNot is : -101
```