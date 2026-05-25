# Lodash _.round() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-round-method/](https://www.geeksforgeeks.org/lodash-_-round-method/)

**Lodash** 是一个工作在下划线.js 之上的 JavaScript 库，Lodash 有助于处理数组、字符串、对象、数字等。

`_.round()` 方法用于计算舍入到精确的数字。

**语法:**

```javascript
_.round(number, [precision = 0])
```

**参数:** 该方法接受两个参数，如上所述，如下所述:

*   `number`: 此参数保存要舍入的数字。
*   `[precision = 0]`: 此参数保存舍入到的精度。

**返回值:** 此方法返回四舍五入后的数字。

**示例 1:** 这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

## JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.round() method
let gfg = _.round(7.56);

// Printing the output
console.log(gfg);
```

**输出:**

```
8
```

## 示例 2

## JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.round() method
let gfg = _.round(9.005, 2);

// Printing the output
console.log(gfg);
```

**输出:**

```
9.01
```

## 示例 3

## JavaScript

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.round() method
let gfg = _.round(1980, -2);

// Printing the output
console.log(gfg);
```

**输出:**

```
2000
```