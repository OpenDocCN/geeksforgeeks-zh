# `_.lowerCase()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-lowercase-method/](https://www.geeksforgeeks.org/lodash-_-lowercase-method/)

`Lodash` 是一个工作在 `underscore.js` 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.lowerCase()` 方法用于将给定的字符串（以空格分隔的单词）转换为小写。

**语法：**
```javascript
_.lowerCase([string=''])
```

**参数：** 该方法接受如上所述的单个参数，描述如下：
* `string`：此参数保存需要转换成小写的字符串。

**返回值：** 该方法返回小写字符串。

**例 1：**

## Javascript
```javascript
const _ = require('lodash');

var str1 = _.lowerCase("GEEKS FOR GEEKS");
console.log(str1);

var str2 = _.lowerCase("GFG--Geeks");
console.log(str2);
```

**输出：**
```
"geeks for geeks"
"gfg geeks"
```

**例 2：**

## Javascript
```javascript
const _ = require('lodash');

var str1 = _.lowerCase("GEEKS__FOR__GEEKS");
console.log(str1);

var str2 = _.kebabCase("G4G--geeks--GEEKS");
console.log(str2);

var str3 = _.kebabCase("GEEKS-----FOR_____Geeks");
console.log(str3);
```

**输出：**
```
"geeks for geeks"
"g-4-g-geeks-geeks"
"geeks-for-geeks"
```