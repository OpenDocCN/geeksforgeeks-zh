# `_.capitalize()` 方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-capitalize-method/](https://www.geeksforgeeks.org/lodash-_-capitalize-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.capitalize()` 方法用于将字符串的第一个字符转换为大写，其余字符转换为小写。

**语法：**

```javascript
_.capitalize([string=''])
```

**参数：** 该方法接受如上所述的单个参数，描述如下：

*   `string`：此参数保存需要将第一个字符转换为大写字符，剩余字符转换为小写字符的字符串。

**返回值：** 该方法返回大写字符串。

## 示例 1

```javascript
const _ = require('lodash');

var str1 = _.capitalize("GEEKSFORGEEKS");
console.log(str1);

var str2 = _.capitalize("GFG--Geeks");
console.log(str2);
```

**输出：**

```javascript
"Geeksforgeeks"
"Gfg--geeks"
```

## 示例 2

```javascript
const _ = require('lodash');

var str1 = _.capitalize("GEEKS__FOR__GEEKS");
console.log(str1);

var str2 = _.capitalize("GEEKS FOR Geeks");
console.log(str2);

var str3 = _.capitalize("geeks--FOR--geeks");
console.log(str3);
```

**输出：**

```javascript
"Geeks__for__geeks"
"Geeks for geeks"
"Geeks--for--geeks"
```