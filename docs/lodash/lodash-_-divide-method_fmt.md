# Lodash _.divide() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-divide-method/](https://www.geeksforgeeks.org/lodash-_-divide-method/)

`_.divide()` 方法用于将两个数字相除。

## 语法

```
_.divide(dividend, divisor)
```

## 参数

该方法接受两个参数，如下所述：

*   Dividend: 此参数保存除法中的第一个数字。
*   Divisor: 此参数保存除法中的第二个数字。

## 返回值

该方法返回两个数除后的商。

## 示例 1

这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.divide() method
let gfg = _.divide(1508, 4);

// Printing the output
console.log(gfg)
```

**输出:**

```
377
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.divide() method
let gfg = _.divide(12, 5);

// Printing the output
console.log(gfg)
```

**输出:**

```
2.4
```