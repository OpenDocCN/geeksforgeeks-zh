# `util.types.isFloat32Array()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-util-types-isfloat32array-method/](https://www.geeksforgeeks.org/node-js-util-types-isfloat32array-method/)

`util.types.isFloat32Array()`方法是`util`模块的内置应用编程接口，用于对Node.js中的`Float32Array`进行类型检查。

## 语法

```js
util.types.isFloat32Array( value )
```

## 参数

该方法接受如上所述和如下所述的单个参数。

*   `value`: 一个任何数据类型的必需参数。

## 返回值

这将返回一个布尔值，如果该值是`Float32Array`，则返回`true`，否则返回`false`。

下面的例子说明了`util.types.isFloat32Array()`方法在Node.js中的使用:

## 示例 1

```js
// Node.js program to demonstrate the   
// util.types.isFloat32Array() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter of
// util.types.isFloat32Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();
var v3 = new Float32Array();
var v4 = new ArrayBuffer();
var v5 = new Float64Array();

// Printing the returned value from
// util.types.isFloat32Array() method
console.log(util.types.isFloat32Array(v1));
console.log(util.types.isFloat32Array(v2));
console.log(util.types.isFloat32Array(v3));
console.log(util.types.isFloat32Array(v4));
console.log(util.types.isFloat32Array(v5));
```

**输出:**

```js
false
false
true
false
false
```

## 示例 2

```js
// Node.js program to demonstrate the   
// util.types.isFloat32Array() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter of 
// util.types.isFloat32Array() method
var v1 = new Float32Array();
var v2 = new Float64Array();

// Calling util.types.isFloat32Array() method
if (util.types.isFloat32Array(v1))
    console.log("The passed value is a Float32Array.");
else
    console.log("The passed value is not a Float32Array");

if (util.types.isFloat32Array(v2))
    console.log("The passed value is a Float32Array.");
else
    console.log("The passed value is not a Float32Array");
```

**输出:**

```js
The passed value is a Float32Array.
The passed value is not a Float32Array
```

**注意:** 以上程序使用`node filename.js`命令编译运行。

**参考:** [https://nodejs.org/api/util.html#util_util_types_isfloat32array_value](https://nodejs.org/api/util.html#util_util_types_isfloat32array_value)