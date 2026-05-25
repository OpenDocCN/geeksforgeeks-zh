# Lodash _.ternary() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-ternary-method/](https://www.geeksforgeeks.org/lodash-_-ternary-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

`_.ternary()` 方法返回一个新的函数，该函数只接受三个参数，并将这些参数传递给给定的函数。给出的任何附加参数都将被丢弃。

**语法:**

```javascript
_.ternary( fun )
```

**参数:** 该方法采用上面列出的单个参数，讨论如下:

*   `fun`: 这是应该用于参数的函数。

**返回值:** 这个方法返回一个新的函数。

**注意:** 这个方法在正常的 JavaScript 中不会工作，因为它需要安装 Lodash contrib 库。可以使用 `npm install lodash-contrib --save` 来安装 `lodash-contrib` 库。

### 例 1

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to be used
function fun() {
    return arguments;
}

// Making the ternary function
var gfgFunc = _.ternary(fun);

console.log("Arguments are :",
    gfgFunc("first", "second", "third"));
```

**输出:**

```
Arguments are : [Arguments] 
  { '0': 'first', '1': 'second', '2': 'third' }
```

### 例 2

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to be used
function fun() {
    return arguments;
}

// Making the ternary function
var gfgFunc = _.ternary(fun);

// Arguments more than 3 are excluded
console.log("Arguments are :",
    gfgFunc("a", "b", "c", "d", "e", "f"));
```

**输出:**

```
Arguments are : [Arguments] { '0': 'a', '1': 'b', '2': 'c' }
```

### 例 3

在本例中，我们将添加参数，但只有前 3 个参数将使用此方法。

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Function to be used
function add() {
    s = 0;
    for (i = 0; i < 3; i++) {
        s += arguments[i];
    }
    return s;
}

// Making the ternary function
var gfgFunc = _.ternary(add);

// Arguments more than 3 are excluded
console.log("Sum of first 3 arguments is :",
    gfgFunc(100, 100, 1000, 4, 5, 6, 7));
```

**输出:**

```
Sum of first 3 arguments is : 1200
```