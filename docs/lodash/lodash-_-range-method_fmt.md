# Lodash _.range() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-range-method/](https://www.geeksforgeeks.org/lodash-_-range-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.range()` 方法用于创建从给定的起始值到但不包括结束值的数字数组。如果指定了负的开始值而没有结束或步骤，则使用 -1 的步骤。如果没有指定结束，则设置为从开始开始，然后设置为 0。

## 语法

```
_.range( start, end, step )
```

## 参数

该方法接受三个参数，如下所述：

*   `start`: 是一个指定范围开始的数字。它是一个可选值。默认值为 0。
*   `end`: 是一个指定范围结束的数字。
*   `step`: 是一个数字，指定范围内的值递增或递减的量。默认值为 1。

## 返回值

返回给定数字范围的数组。

## 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Using the _.range() method
let range_arr = _.range(5);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[0, 1, 2, 3, 4]
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Using the _.range() method
// with the step taken as 2
let range_arr = _.range(0,10,2);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[0, 2, 4, 6, 8]
```

## 示例 3

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Using the _.range() method
// with the step taken as -2
let range_arr = _.range(-1,-11,-2);

// Printing the output
console.log(range_arr);
```

**输出:**

```
[-1, -3, -5, -7, -9]
```