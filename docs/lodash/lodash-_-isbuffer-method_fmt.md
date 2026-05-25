# `_.isBuffer()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isbuffer-method/](https://www.geeksforgeeks.org/lodash-_-isbuffer-method/)

`_.isBuffer()` 方法检查给定值是否为缓冲区。

## 语法

```
_.isBuffer( value )
```

## 参数

该方法接受如上所述的单个参数，描述如下:

*   `value`: 此参数存储要检查的缓冲区的值。

## 返回值

该方法返回一个布尔值（如果给定值是一个缓冲区，则返回 `true`，否则返回 `false`）。

## 示例 1

当值为 `Buffer` 时，此方法返回 `true`。

```
// Defining Lodash variable
const _ = require('lodash');

var val = new Buffer(2);

// Checking for Buffer
console.log("The Value is Buffer : " + _.isBuffer(val));
```

## 输出

```
The Value is Buffer : true
```

## 示例 2

```
// Defining Lodash variable
const _ = require('lodash');

var val = new Uint8Array(2);

// Checking for Buffer
console.log("The Value is Buffer : " + _.isBuffer(val));
```

## 输出

```
The Value is Buffer : false
```