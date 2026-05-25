# 洛达什 `_.isArray()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isarray-method/](https://www.geeksforgeeks.org/lodash-_-isarray-method/)

洛达什 `_.isArray()` 方法检查给定值是否可以归类为数组值。

## 语法

```
_.isArray( value )
```

## 参数

该方法接受如上所述的单个参数，描述如下：

* `value`: 此参数保存要检查的数组值。

## 返回值

该方法返回一个布尔值。

## 例 1：当此方法返回 `true` 时

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = [1, 2, 3]

// Checking for an Array
console.log("The Value is Array : "
    +_.isArray(val));
```

**输出：**

```
The Value is Array : true
```

## 例 2：当此方法返回 `false` 时（字符串）

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = "GeeksforGeeks"

// Checking for an Array
console.log("The Value is Array : "
    +_.isArray(val));
```

**输出：**

```
The Value is Array : false
```

## 例 3

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = { 1:1 }

// Checking for an Array
console.log("The Value is Array : "
    +_.isArray(val));
```

**输出：**

```
The Value is Array : false
```

**注意：** 这在正常的 JavaScript 中不会起作用，因为它需要安装 lodash 库。