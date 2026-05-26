# 下划线.js _.curry()方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-curry-method/](https://www.geeksforgeeks.org/underscore-js-_-curry-method/)

下划线库的 `_.curry()` 方法返回给定函数的柯里化版本。如果设置了相应标志，参数将从右向左处理。

## 语法

```
_.curry( fun, reverse )
```

## 参数

该方法接受两个参数，如上所列，具体说明如下。

*   `fun`：这是给定的函数。
*   `reverse`：这是一个可选参数，用于决定参数是否反转处理。

## 返回值

返回函数的柯里化版本。

## 注意

要执行以下示例，您必须使用此命令安装 `underscore-contrib` 库。

```
npm install underscore-contrib
```

## 例 1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Function
function fun(a, b, c, d){
    return a + b + c + d;
}

// Making curried function
var gfgFunc = _.curry(fun);

// Only operates for arguments same
// as the number in function
console.log("Addition is :",
        gfgFunc(2)(23)(2)(3));

// Not adds for less arguments
console.log(gfgFunc(1)(2));
```

**输出：**

```
Addition is : 30
[Function: mustBeUnary]
```

## 例 2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Function
function fun(a, b, c) {
    return a * b * c;
}

// Making curried function
var gfgFunc = _.curry(fun);

// Only operates for arguments same
// as the number in function
console.log("Multiplication is :",
        gfgFunc(2)(23)(2));

// Not multiplies for less arguments
console.log(gfgFunc(1)(2));
```

**输出：**

```
Multiplication is : 92
[Function: mustBeUnary]
```

## 例 3：参数从右向左处理（reverse = true）

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Function
function fun(a, b, c){
    return arguments;
}

// Making curried function
var gfgFunc = _.curry(fun,true);

// Only operates for arguments same
// as the number in function
console.log("curried arguments are :",
    gfgFunc("arg1")("arg2")("arg3"));
```

**输出：** 参数以相反的顺序存储。

```
curried arguments are : [Arguments]
    { '0': 'arg3', '1': 'arg2', '2': 'arg1' }
```

## 例 4：参数从左到右处理（reverse = false）

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

// Function
function fun(a, b, c){
    return arguments;
}

// Making curried function
var gfgFunc = _.curry(fun,false);

// Only operates for arguments same
// as the number in function
console.log("curried arguments are :",
    gfgFunc("arg1")("arg2")("arg3"));
```

**输出：**

```
curried arguments are : [Arguments]
    { '0': 'arg1', '1': 'arg2', '2': 'arg3' }
```