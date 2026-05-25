# Lodash _.isEmpty() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isempty-method/](https://www.geeksforgeeks.org/lodash-_-isempty-method/)

Lodash `_.isEmpty()` 方法检查值是否为空对象、集合、Map 或 Set。对象如果没有自己的可枚举字符串键控属性，则被认为是空的。如果集合的长度为 0，则它们被认为是空的。同样，如果 Map 和 Set 的大小为 0，则它们被认为是空的。

## 语法

```javascript
_.isEmpty( value )
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`: 此参数存储需要被检查是否为 null 的值。

## 返回值

该方法返回一个**布尔值**（如果给定值为空，则返回 `true`，否则返回 `false`）。

## 例 1

当值为空时，该方法返回 **真**。

```javascript
// Defining Lodash variable
const _ = require('lodash');

// Checking for Empty Value
console.log("The Value is Empty : "
        +_.isEmpty(null));
```

**输出:**

```text
The Value is Empty : true
```

## 例 2

当数组为空时，此方法返回 **真**。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = []

// Checking for Empty Value
console.log("The Value is Empty : "
        +_.isEmpty(val));
```

**输出:**

```text
The Value is Empty : true
```

## 例 3

该方法返回 **真** 为布尔值。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = false;

// Checking for Empty Value
console.log("The Value is Empty : " 
        +_.isEmpty(val));
```

**输出:**

```text
The Value is Empty : true
```

## 例 4

在这个例子中，该方法将返回 **假**。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = { "a": 1 };

// Checking for Empty Value
console.log("The Value is Empty : " 
        +_.isEmpty(val)); 
```

**输出:**

```text
The Value is Empty : false
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 lodash 库。

可以使用 `npm install lodash` 安装 Lodash 库。