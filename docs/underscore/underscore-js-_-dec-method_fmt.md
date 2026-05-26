# 下划线.js `_.dec()`方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-dec-method/](https://www.geeksforgeeks.org/underscore-js-_-dec-method/)

`_.dec()`方法通过将给定值递减1来返回结果。

**语法：**

```javascript
_.dec( value );
```

**参数：** 该方法取值并递减。

**返回值：** 此方法通过给定值减1来返回结果。

**注意：** 这在正常的JavaScript中无法工作，因为它需要安装下划线.js contrib库。可以使用`npm install underscore-contrib`来安装下划线.js contrib库。

## 例1

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var val = 33
var decrVal = _.dec( val );

console.log("The Given value is :", val);
console.log("The Decrement of Given value is :", decrVal);
```

**输出：**

```
The Given value is : 33
The Decrement of Given value is : 32
```

## 例2

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var val = 100
var decrVal = _.dec( val );

console.log("The Given value is :", val);
console.log("The Decrement of Given value is :", decrVal);
```

**输出：**

```
The Given value is : 100
The Decrement of Given value is : 99
```