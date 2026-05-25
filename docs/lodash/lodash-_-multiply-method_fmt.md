# `_.multiply()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-multiply-method/](https://www.geeksforgeeks.org/lodash-_-multiply-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、字符串、对象、数字等。

`_.multiply()` 方法用于将参数中给定的两个数相乘，并返回结果。

**语法:**

```javascript
_.multiply( multiplier, multiplicand )
```

**参数:** 该方法接受两个参数，如上所述，如下所述:

*   `multiplier`: 此参数保存乘法中的第一个数字。
*   `multiplicand`: 此参数保存乘法中的第二个数字。

**返回值:** 此方法返回两个数的乘积。

**例 1:**

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.multiply() method
let ans = _.multiply(15, 8);

// Printing the output
console.log(ans);
```

**输出:**

```
120
```

**例二:**

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.multiply() method
let ans = _.multiply(23, -9);

// Printing the output
console.log(ans);
```

**输出:**

```
-207
```