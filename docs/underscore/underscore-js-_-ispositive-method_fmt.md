# 下划线.js `_.isPositive()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-ispositive-method/](https://www.geeksforgeeks.org/underscore-js-_-ispositive-method/)

`_.isPositive()`方法检查给定值是否为正，相应返回一个布尔值。

## 语法

```javascript
_.isPositive(value);
```

## 参数

该方法接受如上所述的单个参数，如下所述:

*   `value`: 要检查正值的给定值。

## 返回值

该方法返回一个`布尔值`（如果给定值为正，则返回真，否则返回假）。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装下划线.js contrib 库。

下划线.js contrib 库可以使用安装 `npm install underscore-contrib-save`。

## 示例 1

### JavaScript

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Positive : " +_.isPositive(20));
```

### 输出

```
The Value is Positive : true
```

## 示例 2

### JavaScript

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Positive : " +_.isPositive(-1000));
```

### 输出

```
The Value is Positive : false
```

## 示例 3

对于包含正值的字符串，此方法返回 true

### JavaScript

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Positive : " +_.isPositive("100"));
```

### 输出

```
The Value is Positive : true
```