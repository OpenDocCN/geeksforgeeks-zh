# `util.types.isUint32Array()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-util-types-isuint32array-method/](https://www.geeksforgeeks.org/node-js-util-types-isuint32array-method/)

`util.types.isUint32Array()` (在 v10.0.0 中添加) 方法是 `util` 模块的内置应用程序编程接口，用于检查传递的值在 Node.js 中是否属于类型 `Uint32Array`，即无符号 32 位数组，范围从 `0` 到 `4294967295`，内存大小为 4 字节。如果传递的值属于 `Uint32Array` 类型，则返回 `true`，否则返回 `false`。

## 语法

```js
const util = require('util');
util.types.isUint32Array( value )
```

## 参数

该方法接受如上所述的单个参数，如下所述。

*   `value` <`any`>: 它是接受任意变量、类、函数、对象或 JavaScript 原语或任意数据类型的必需参数。

## 返回值

<`boolean`>: 这返回一个布尔值。如果传递的值是 `Uint32Array` 类型，则返回 `true`，否则返回 `false`。

下面的例子说明了在 Node.js 中 `util.types.isUint32Array()` 方法的使用。

## 示例 1

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// util.types.isUint32Array() method

// Using require to access util module
const util = require('util');
const { types } = require('util');

// Passing ArrayBuffer as parameter
console.log("1.>", util.types.isUint32Array(
        new ArrayBuffer()));
// Returns false

// Passing Uint16Array with argument as parameter
console.log("2.>", util.types.isUint32Array(
        new Uint16Array(64)));
// Returns true

// Passing UintArray with JSON data as parameter
console.log("3.>", util.types.isUint32Array(
    new Uint32Array([{
    1: '1',
    5: "hii", f: '8', a: 1, af: 4294967295
}])));
// Returns true

// Passing Uint32Array as parameter
console.log("4.>", util.types.isUint32Array(
        new Uint32Array()));
// Returns true

// Passing data as parameter from 0 to 4294967295
console.log("5.>", util.types.isUint32Array(
    new Uint32Array([1, 5, 8, 1, 4294967295])));
// Returns true

// Passing Float64Array as parameter
console.log("6.>", util.types.isUint32Array(
            new Float64Array(64)));
// Returns false

// Passing Int8Array as parameter
console.log("7.>", util.types.isUint32Array(
            new Int8Array(8)));
// Returns false
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> 1.> false
>
> 2.> false
>
> 3.> true
>
> 4.> true
>
> 5.> true
>
> 6.> false
>
> 7.> false

## 示例 2

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// util.types.isUint32Array() method

// Using require to access util module
const util = require('util');
const { types } = require('util');

// Passing BigInt64Array as parameter
console.log("1.>", util.types.isUint32Array(
            new BigInt64Array()));
// Returns false

// Passing BigUint64Array as parameter
console.log("2.>", util.types.isUint32Array(
            new BigUint64Array()));
// Returns false

// Passing Float32Array as parameter
console.log("3.>", util.types.isUint32Array(
            new Uint32Array()));
// Returns false

// Passing Int8Array as parameter
console.log("4.>", util.types.isUint32Array(
            new Int8Array()));
// Returns false

// Passing Int16Array as parameter
console.log("5.>", util.types.isUint32Array(
            new Int16Array()));
// Returns false

// Passing Uint8Array as parameter
console.log("6.>", types.isUint32Array(
            new Uint8Array()));
// Returns false

// Passing Float64Array as parameter
console.log("7.>", types.isUint32Array(
            new Float64Array()));
// Returns false

var var1 = new Uint32Array();
var var2 = new Int16Array();

// Calling util.types.isUint32Array() method
if (util.types.isUint32Array(var1))
    console.log("Yes, the value is a isUint32Array.");
else
    console.log("No, provided value is not a isUint32Array");

// Calling util.types.isUint32Array() method
if (util.types.isUint32Array(var2))
    console.log("Yes, the value is a isUint32Array.");
else
    console.log("No, provided value is not a isUint32Array");
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> 1.> false
>
> 2.> false
>
> 3.> true
>
> 4.> false
>
> 5.> false
>
> 6.> false
>
> 7.> false
>
> Yes, the value is a isUint32Array.
>
> No, provided value is not a isUint32Array

**参考:** [https://nodejs.org/api/util.html#util_util_types_isuint32array_value](https://nodejs.org/api/util.html#util_util_types_isuint32array_value)