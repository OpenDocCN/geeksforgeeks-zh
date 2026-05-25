# Lodash _.rangeRight() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-rangeright-method/](https://www.geeksforgeeks.org/lodash-_-rangeright-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.rangeRight()` 方法用于创建一个数字数组，该数组从给定的 `start` 值到给定的 `end` 值（但不包括 `end` 值本身）。它以降序填充这些值。如果指定了一个负的 `start` 而没有 `end` 或 `step`，则使用 -1 作为 `step` 值。如果没有指定 `end`，则将其设置为 `start`，然后将 `start` 设置为 0。

## 语法

```
_.rangeRight( start, end, step )
```

## 参数

该方法接受三个参数，如下所述：

*   `start`: 一个指定范围开始的数字。它是可选的。默认值为 0。
*   `end`: 一个指定范围结束的数字。
*   `step`: 一个数字，指定范围内的值递增或递减的量。默认值为 1。

## 返回值

返回一个数组，数组中的数字范围按降序排列。

## 例 1

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// Using the _.rangeRight() method
let range_arr = _.rangeRight(6);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[5, 4, 3, 2, 1, 0]
```

## 例 2

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// Using the _.rangeRight() method
// with the step taken as 3
let range_arr = _.rangeRight(0,15,3);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[12, 9, 6, 3, 0]
```

## 例 3

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// Using the _.rangeRight() method
// with the step taken as -2
let range_arr = _.rangeRight(0,-10,-2);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[-8, -6, -4, -2, 0]
```