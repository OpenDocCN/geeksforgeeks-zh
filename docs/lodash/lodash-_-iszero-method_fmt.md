# `_.isZero()` 方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-iszero-method/](https://www.geeksforgeeks.org/lodash-_-iszero-method/)

`_.isZero()` 方法检查给定值是否为零值，并返回相应的布尔值。

## 语法

```javascript
_.isZero(value);
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`：要检查的给定零值。

## 返回值

如果给定值为零，该方法返回布尔值 `true`，否则返回 `false`。

## 注意

这在普通的 JavaScript 中无法工作，因为它需要安装 `lodash-contrib` 库。可以使用以下命令安装：

```bash
npm install lodash-contrib
```

## 示例 1

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib');

// Checking for _.isZero() method 
console.log("The Value is Zero : " + _.isZero(0));

console.log("The Value is Zero : " + _.isZero(10));

console.log("The Value is Zero : " + _.isZero(true));
```

**输出：**

```
The Value is Zero : true
The Value is Zero : false
The Value is Zero : false
```

## 示例 2

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib');

// Checking for _.isZero() method 
console.log("The Value is Zero : " + _.isZero(false));

console.log("The Value is Zero : " + _.isZero("0"));

console.log("The Value is Zero : " + _.isZero({}));
```

**输出：**

```
The Value is Zero : false
The Value is Zero : false
The Value is Zero : false
```