# Node.js `util.types.isDate()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isdate-method/](https://www.geeksforgeeks.org/node-js-util-types-isdate-method/)

`util.types.isDate()` 方法是 `util` 模块的内置 API，用于检查 Node.js 中日期的类型。

## 语法

```js
util.types.isDate( value )
```

## 参数

该方法接受如上所述和如下所述的单个参数。

*   `value`：一个必需的参数，可以是任何数据类型。

## 返回值

返回一个布尔值，如果该值是日期对象，则为 `true`，否则为 `false`。

下面的例子说明了 `util.types.isDate()` 方法在 Node.js 中的使用：

## 示例 1

```js
// Node.js program to demonstrate the   
// util.types.isDate() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isDate() method
var v1 = new Date();
var v2 = 3 / 6 / 96;

// Printing the returned value from
// util.types.isDate() method
console.log(util.types.isDate(v1));
console.log(util.types.isDate(v2));
```

**输出：**

```js
true
false
```

## 示例 2

```js
// Node.js program to demonstrate the   
// util.types.isDate() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isDate() method
var v1 = new Date();
var v2 = 3 / 6 / 96;

// Calling util.types.isDate() method
if (util.types.isDate(v1))
    console.log("The passed value is a Date.");
else
    console.log("The passed value is not a Date");

if (util.types.isDate(v2))
    console.log("The passed value is a Date.");
else
    console.log("The passed value is not a Date");
```

**输出：**

```js
The passed value is a Date.
The passed value is not a Date
```

## 注意

以上程序使用 `node filename.js` 命令编译运行。

## 参考

[https://nodejs.org/api/util.html#util_util_types_isdate_value](https://nodejs.org/api/util.html#util_util_types_isdate_value)