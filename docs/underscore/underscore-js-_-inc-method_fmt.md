# Underscore.js `_.inc()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-inc-method/](https://www.geeksforgeeks.org/underscore-js-_-inc-method/)

`_.inc()`方法通过将给定值增加1来返回结果。

**语法:**
```javascript
_.inc( value );
```

**参数:** 该方法取值并递增。

**返回值:** 此方法通过给定值增加1来返回结果。

**注意:** 这在正常的JavaScript中无法工作，因为它需要安装Underscore.js contrib库。

可以使用`npm install underscore-contrib --save`来安装Underscore.js contrib库。

**例1:**
```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var val = 100
var incrVal = _.inc( val );

console.log("The Given value is :",val);
console.log("The Increment of Given value is :",incrVal);
```

**输出:**
```
The Given value is : 100
The Increment of Given value is : 101
```

**例2:**
```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var val = 51
var incrVal = _.inc( val );

console.log("The Given value is :",val);
console.log("The Increment of Given value is :",incrVal);
```

**输出:**
```
The Given value is : 51
The Increment of Given value is : 52
```