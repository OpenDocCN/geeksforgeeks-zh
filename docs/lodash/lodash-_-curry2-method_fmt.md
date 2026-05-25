# Lodash `_.curry2()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-curry2-method/](https://www.geeksforgeeks.org/lodash-_-curry2-method/)

Lodash `_.curry2()` 方法返回给定函数的柯里化版本，但会将参数数量固定为两个，不多不少。

**语法:**

```javascript
_.curry2( fun )
```

**参数:** 该方法采用如上所列的单个参数，讨论如下。

*   `fun`: 这是给定的函数。

**返回值:** 返回函数的柯里化版本。

**注意:** 要执行以下示例，您必须使用此命令提示符安装 `lodash-contrib` 库，并执行以下命令。

```bash
npm install lodash-contrib
```

## 例 1

### JavaScript

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(a, b){
    return a * b;
}

// Making curried function
var gfgFunc = _.curry2(fun);

// Only operates for exactly two arguments
console.log("Multiplication is :",
    gfgFunc(2)(23));
```

**输出:**

```
Multiplication is : 46
```

## 例 2

### JavaScript

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(a, b){
    return a + b;
}

// Making curried function
var gfgFunc = _.curry2(fun);

// Only operates for exactly two arguments
console.log("Addition is :", gfgFunc(25)(23));
```

**输出:**

```
Addition is : 48
```

## 例 3

### JavaScript

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function
function fun(x, y){
    return arguments;
}

// Making curried function
var gfgFunc = _.curry2(fun);

// Shows only two arguments
console.log("Curried Arguments are :",
    gfgFunc("arg1")("arg2"));
```

**输出:**

```
Curried Arguments are : [Arguments] 
    { '0': 'arg1', '1': 'arg2' }
```