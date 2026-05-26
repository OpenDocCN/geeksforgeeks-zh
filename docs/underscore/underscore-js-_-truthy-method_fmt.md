# _.truthy() 方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-truthy-method/](https://www.geeksforgeeks.org/underscore-js-_-truthy-method/)

`_.truthy()` 方法检查给定值是否 truthy，相应返回一个布尔值。一个 truthy 值是在布尔上下文中强制为 `true` 的值。

## 语法

```
_.truthy( value );
```

## 参数

*   `value`: 要检查真实值的给定值。

## 返回值

该方法返回一个布尔值（如果给定值为真，则返回 `true`，否则返回 `false`）。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 `underscore-contrib` 库。

可以使用 `npm install underscore-contrib` 来安装 `underscore-contrib` 库。

## 示例

### 示例 1
真布尔始终返回真。

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bool = _.truthy(true);

console.log("Given Value is Truthy : ",bool);
```

**输出:**

```
Given Value is Truthy : true
```

### 示例 2
现有值返回真布尔值，因此该方法返回真。

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bool = _.truthy(10);

console.log("Given Value is Truthy : ",bool);
```

**输出:**

```
Given Value is Truthy : true
```

### 示例 3

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bool = _.truthy([ 1, 2, 3 ]);

console.log("Given Value is Truthy : ",bool);
```

**输出:**

```
Given Value is Truthy : true
```

### 示例 4
在传递 `false` 布尔值时，此方法返回 `false`。

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var bool = _.truthy(false);

console.log("Given Value is Truthy : ",bool);
```

**输出:**

```
Given Value is Truthy : false
```