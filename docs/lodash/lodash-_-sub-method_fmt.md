# `_.sub()`方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-sub-method/](https://www.geeksforgeeks.org/lodash-_-sub-method/)

`_.sub()`方法返回所有给定参数的差值。

## 语法

```javascript
_.sub( val1, val2, ..., valn );
```

## 参数

这个方法返回 n 个值来操作它们 `_.sub()`方法。

## 返回值

这个方法返回所有给定参数的差值。

## 注意

这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib --save`。

## 例 1

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

var diff = _.sub( 10, 2, 4, 1 );

console.log("The Difference is : ", diff);
```

**输出：**

```javascript
The Difference is : 3
```

## 例 2

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

var diff = _.sub( 10 );

console.log("The Difference is : ", diff);
```

**输出：**

```javascript
The Difference is : 10
```

## 例 3

```javascript
// Defining lodash contrib variable
var _ = require('lodash-contrib');

var diff = _.sub( 1, 3, 5, 7, 9, 99, 100 );

console.log("The Difference is : ", diff);
```

**输出：**

```javascript
The Difference is : -222
```