# `util.types.isInt8Array()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isint8array-method/](https://www.geeksforgeeks.org/node-js-util-types-isint8array-method/)

`util.types.isInt8Array()`方法是`util`模块的内置应用编程接口，用于对Node.js中的`Int8Array`进行类型检查。

## 语法

```js
util.types.isInt8Array( value )
```

## 参数

该方法接受如上所述和如下所述的单个参数。

*   `value`：一个必需的参数，可以是任何数据类型。

## 返回值

返回布尔值，如果值是`Int8Array`对象，则返回`true`，否则返回`false`。

下面的例子说明了在Node.js中`util.types.isInt8Array()`方法的使用：

## 例 1

```js
// Node.js program to demonstrate the   
// util.types.isInt8Array() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter of
// util.types.isInt8Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();
var v3 = new Float32Array();
var v4 = new ArrayBuffer();
var v5 = new Int8Array();

// Printing the returned value from
// util.types.isInt8Array() method
console.log(util.types.isInt8Array(v1));
console.log(util.types.isInt8Array(v2));
console.log(util.types.isInt8Array(v3));
console.log(util.types.isInt8Array(v4));
console.log(util.types.isInt8Array(v5));
```

### 输出

```js
false
false
false
false
true
```

## 例 2

```js
// Node.js program to demonstrate the   
// util.types.isInt8Array() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter of
// util.types.isInt8Array() method
var v1=new Int8Array();
var v2=new Int16Array();

// Calling util.types.isInt8Array() method
if(util.types.isInt8Array(v1))
    console.log("The passed value is a Int8Array.");
else
    console.log("The passed value is not a Int8Array");

if(util.types.isInt8Array(v2))
    console.log("The passed value is a Int8Array.");
else
    console.log("The passed value is not a Int8Array");
```

### 输出

```js
The passed value is a Int8Array.
The passed value is not a Int8Array
```

**注意：** 以上程序使用`node filename.js`命令编译运行。

**参考：** [https://nodejs.org/api/util.html#util_util_types_isint8array_value](https://nodejs.org/api/util.html#util_util_types_isint8array_value)