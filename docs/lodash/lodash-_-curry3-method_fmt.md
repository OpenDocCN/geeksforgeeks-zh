# Lodash _.curry3() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-curry3-method/](https://www.geeksforgeeks.org/lodash-_-curry3-method/)

Lodash `_.curry3()` 方法返回给定函数的柯里化版本，但是将柯里化正好三个参数，不多也不少。

**语法:**

```
_.curry3( fun )
```

**参数:** 该方法采用如上所列的单个参数，讨论如下。

*   `fun`: 这是给定的函数。

**返回值:** 返回函数的柯里化版本。

**注意:** 要执行以下示例，您必须使用此命令提示符安装 `lodash-contrib` 库，并执行以下命令。

```
npm install lodash-contrib
```

**例 1:**

## JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(a, b, c){
    return a - b - c;
}

// Making curried function
var gfgFunc = _.curry3(fun);

// Only operates for exactly
// three arguments
console.log("Subtraction is :",
    gfgFunc(24)(22)(1));
```

**输出:**

```
Subtraction is : 1
```

**例 2:**

## JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(a, b, c){
    return a + b + c;
}

// Making curried function
var gfgFunc = _.curry3(fun);

// Only operates for exactly
// three arguments
console.log("Addition is :",
    gfgFunc(25)(23)(1));
```

**输出:**

```
Addition is : 49
```

**例 3:**

## JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(x, y, z){
    return arguments;
}

// Making curried function
var gfgFunc = _.curry3(fun);

// Only operates for exactly
// three arguments
console.log("Curried Arguments are :",
    gfgFunc("arg1")("arg2")("arg3"));
```

**输出:**

```
Curried Arguments are : [Arguments]
    { '0': 'arg1', '1': 'arg2', '2': 'arg3' }
```

**例 4:**

## JavaScript

```
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(x, y, z){
    return arguments;
}

// Making curried function
var gfgFunc = _.curry3(fun);

// Only operates for exactly three
// arguments
// For two args, this method returns
// function info
console.log("Curried Arguments are :",
    gfgFunc("arg1")("arg2"));
```

**输出:**

```
[Function: mustBeUnary]
```