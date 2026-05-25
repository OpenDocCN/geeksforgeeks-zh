# Lodash _.iterateUntil() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-iterateuntil-method/](https://www.geeksforgeeks.org/lodash-_-iterateuntil-method/)

Lodash 的 `_.iterateUntil()` 方法接受两个函数和一个种子值（例如 `n`）。其中一个函数用作结果生成器，另一个用作停止检查。该方法返回一个包含每个生成结果的数组。`_.iterateUntil()` 的工作方式是：在开始时将种子值传递给结果生成器，后续的每个结果会继续生成，**直到**其未通过检查函数。

生成器函数被输入起始种子值，因此会生成数组，直到停止检查函数返回 `false`。

**语法:**

```javascript
_.iterateUntil(genFunc, checkFunc, seed_val)
```

**参数:** 该方法接受三个参数，如下所述：

*   `genFunc`: 该函数用作结果生成器。
*   `checkFunc`: 用作停止检查的函数。
*   `seed_val`: 启动时传递给生成器的值。

**返回值:** 这个方法返回一个生成的数组。

**注意:** 这在普通的 JavaScript 环境中无法工作，因为它需要安装 `lodash-contrib` 库。

可以使用 `npm install lodash-contrib --save` 命令安装 `lodash-contrib` 库。

**示例 1:** 在本例中，我们将使用此方法生成一个数组。

## JavaScript 示例

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Defining Generating function
var genFunc = 
    function(n) { 
        return n + 1; 
    }

// Defining stop-check function
var checkFunc = 
    function(n) { 
        return n < 11; 
    }

// Generating an array
var arr = _.iterateUntil(genFunc, checkFunc, 1);
console.log("Generated Array : ");
console.log(arr);
```

**输出:**

```
Generated Array :
[
  2, 3, 4,  5, 6,
  7, 8, 9, 10
]
```

**示例 2:** 在本例中，我们将通过给出种子值 `0` 并从生成函数返回 `n+2`，使用此方法生成一个 2 的倍数的数组。

## JavaScript 示例

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

// Defining Generating function
var genFunc = 
    function(n) { 
        return n + 2; 
    }
// Defining stop-check function
var checkFunc = 
    function(n) { 
        return n < 21; 
    }
// Generating an array
var arr = _.iterateUntil(genFunc, checkFunc, 0);
console.log("Generated Array : ");
console.log(arr);
```

**输出:**

```
Generated Array :
[
   2,  4,  6,  8, 10,
  12, 14, 16, 18, 20
]
```