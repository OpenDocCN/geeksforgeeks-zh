# Underscore.js _.nth() 方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-nth-method/](https://www.geeksforgeeks.org/underscore-js-_-nth-method/)

`_.nth()` 方法获取一个数组和一个索引，并返回该数组中该索引上的元素。

## 语法

```javascript
_.nth(array, index);
```

## 参数

*   `array`: 要从中取元素的给定数组。
*   `index`: 要找到元素的索引。

## 返回值

此方法返回给定索引上的一个元素。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 `underscore-contrib` 库。

可以使用 `npm install underscore-contrib --save` 来安装 `underscore-contrib` 库。

## 示例 1

在本例中，我们将使用此方法从数组中获取一个元素。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');
// Array
var array = [-1, -25, -43, 10, 125, -1];
// Getting nth element
var elem = _.nth(array, 2)
console.log("Original Array : ", array);
console.log("Element: ", elem);
```

**输出:**

```
Original Array :  [ -1, -25, -43, 10, 125, -1 ]
Element:  -43
```

## 示例 2

对于超出索引范围的情况，此方法返回 `undefined`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');
// Array
var array = [-1, -25, -43, 10, 125, -1];
// Getting nth element
var elem = _.nth(array, 100)
console.log("Original Array : ", array);
console.log("Element: ", elem);
```

**输出:**

```
Original Array :  [ -1, -25, -43, 10, 125, -1 ]
Element:  undefined
```

## 示例 3

对于不存在的负索引，此方法返回 `undefined`。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');
// Array
var array = [-1, -25, -43, 10, 125, -1];
// Getting nth element
var elem = _.nth(array, -1)
console.log("Original Array : ", array);
console.log("Element: ", elem);
```

**输出:**

```
Original Array :  [ -1, -25, -43, 10, 125, -1 ]
Element:  undefined
```