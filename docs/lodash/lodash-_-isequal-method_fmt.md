# 洛达什 `_.isEqual()`方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-isequal-method/](https://www.geeksforgeeks.org/lodash-_-isequal-method/)

洛达什 `_.isEqual()`方法对两个值进行深度比较，以确定它们是否相等。此方法支持比较数组、数组缓冲区、布尔值、日期对象、映射、数字、对象、正则表达式、集合、字符串、符号和类型化数组。

**语法：**

```
_.isEqual( value1, value2)
```

**参数：** 该方法接受两个参数，如上所述，如下所述：

*   `value1`：被检查的第一个值。
*   `value2`：被检查的第二个值。

**返回值：** 该方法返回一个布尔值（如果两个值相等则返回真，否则返回假）。

## 例 1：对象比较

```javascript
// Defining Lodash variable 
const _ = require('lodash');

var val1 = { "a": "gfg" };

var val2 = { "a": "gfg" };

// Checking for Equal Value 
console.log("The Values are Equal : "
        +_.isEqual(val1,val2));
```

**输出：**

```
The Values are Equal : true
```

## 例 2：数组比较

```javascript
// Defining Lodash variable 
const _ = require('lodash');

var val1 = [1, 2, 3, 4]

var val2 = [1, 2, 3, 4]

// Checking for Equal Value 
console.log("The Values are Equal : "
        +_.isEqual(val1,val2));
```

**输出：**

```
The Values are Equal : true 
```

## 例 3：字符串比较

```javascript
// Defining Lodash variable 
const _ = require('lodash');

var val1 = "gfg"

var val2 = "gfg"

// Checking for Equal Value 
console.log("The Values are Equal : "
        +_.isEqual(val1,val2));
```