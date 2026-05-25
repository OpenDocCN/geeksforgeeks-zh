# 洛达什 `_.isArrayBuffer()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isarraybuffer-method/](https://www.geeksforgeeks.org/lodash-_-isarraybuffer-method/)

洛达什 `_.isArrayBuffer()` 方法检查给定的对象或值是否可以归类为 `ArrayBuffer` 值。

## 语法

```
_.isArrayBuffer( value )
```

## 参数

该方法接受如上所述的单个参数，如下所述:

*   `value`: 此参数保存需要检查是否为 `ArrayBuffer` 的值。

## 返回值

该方法返回一个布尔值。

## 例 1: 当此方法返回 `true` 时

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = new ArrayBuffer(3)
// Checking for an ArrayBuffer
console.log("The Value is ArrayBuffer : " 
    +_.isArrayBuffer(val)); 
```

**输出:**

```
The Value is ArrayBuffer : true
```

## 例 2: 当此方法返回 `false` 时（字符串）

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = "GeeksforGeeks"

// Checking for an ArrayBuffer
console.log("The Value is Array : "
    +_.isArrayBuffer(val)); 
```

**输出:**

```
The Value is ArrayBuffer : false
```

## 例 3

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = { 1:1 }

// Checking for an ArrayBuffer
console.log("The Value is Array : " 
    +_.isArrayBuffer(val)); 
```

**输出:**

```
The Value is ArrayBuffer : false
```

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 `lodash` 库，并且可以使用 `npm install lodash` 进行安装。