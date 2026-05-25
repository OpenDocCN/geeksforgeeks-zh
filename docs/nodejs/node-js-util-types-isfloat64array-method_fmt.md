# `util.types.isFloat64Array()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-util-types-isfloat64array-method/](https://www.geeksforgeeks.org/node-js-util-types-isfloat64array-method/)

`util.types.isFloat64Array()` 方法是 `util` 模块的内置 API，用于检查 Node.js 中的 `Float64Array` 类型。

## 语法

```js
util.types.isFloat64Array( value )
```

## 参数

该方法接受如上所述的单个参数，如下所述：

*   `value`: 这是一个必需参数，用于保存任何数据类型。

## 返回值

返回一个布尔值，如果该值是 `Float64Array`，则为 `true`，否则为 `false`。

下面的例子说明了 `util.types.isFloat64Array()` 方法在 Node.js 中的使用：

## 示例 1

```js
// Node.js program to demonstrate the
// util.types.isFloat64Array() Method

// Allocating util module
const util = require('util');

// Passed as parameter to the
// util.types.isFloat64Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();
var v3 = new Float32Array();
var v4 = new ArrayBuffer();
var v5 = new Float64Array();

// Printing the returned value from
// util.types.isFloat64Array() method
console.log(util.types.isFloat64Array(v1));
console.log(util.types.isFloat64Array(v2));
console.log(util.types.isFloat64Array(v3));
console.log(util.types.isFloat64Array(v4));
console.log(util.types.isFloat64Array(v5));
```

**输出：**

```js
false
false
false
false
true
```

## 示例 2

```js
// Node.js program to demonstrate the
// util.types.isFloat64Array() Method

// Allocating util module
const util = require('util');

// To be passed as parameter of
// util.types.isFloat64Array() method
var v1 = new Float32Array();
var v2 = new Float64Array();

// Calling util.types.isFloat64Array() method
if (util.types.isFloat64Array(v1))
    console.log("The passed value is a Float64Array.");
else
    console.log("The passed value is not a Float64Array");

if (util.types.isFloat64Array(v2))
    console.log("The passed value is a Float64Array.");
else
    console.log("The passed value is not a Float64Array");
```

**输出：**

```js
The passed value is not a Float64Array
The passed value is a Float64Array.
```

**注意：** 以上程序使用 `node filename.js` 命令编译运行。

**参考：** [https://nodejs.org/api/util.html#util_util_types_isfloat64array_value](https://nodejs.org/api/util.html#util_util_types_isfloat64array_value)