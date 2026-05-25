# `util.types.isUint8ClampedArray()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isuint8clampedarray-method/](https://www.geeksforgeeks.org/node-js-util-types-isuint8clampedarray-method/)

`util.types.isUint8ClampedArray()` 方法是 `util` 模块的内置 API，主要是为了支持 Node.js 自身内部 API 的需求而设计的。

`util.types.isUint8ClampedArray()` 方法用于检查给定值是否为无符号 8 位钳制整数数组。

## 语法

```js
util.types.isUint8ClampedArray( value )
```

## 参数

该函数接受如上所述的单个参数，如下所述：

*   `value`：此值将被检查是否为 8 位无符号钳制整数数组。

## 返回值

如果传递的值是无符号 8 位钳制整数数组，则返回布尔值，即 `true`，否则返回 `false`。

下面的例子说明了 Node.js 中的 `util.types.isUint8ClampedArray()` 方法：

## 示例 1

```js
// Node.js program to demonstrate the
// util.types.isUint8ClampedArray() method

// Import the util module
const util = require('util');

// Checking for a unsigned 8-bit
// clamped integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                    new Uint8ClampedArray());

console.log("Object is Unsigned 8-bit clamped array"
                  + " object:", isUint8ClampedArr);

// Checking for a unsigned 8-bit
// unclamped integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                    new Uint8Array());

console.log("Object is Unsigned 8-bit clamped"
                  + " array object:", isUint8ClampedArr);

// Checking for a integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                  new Int8Array());

console.log("Object is Unsigned 8-bit clamped "
                  + "array object:", isUint8ClampedArr);
```

**输出：**

```js
Object is Unsigned 8-bit clamped array object: true
Object is Unsigned 8-bit clamped array object: false
Object is Unsigned 8-bit clamped array object: false
```

## 示例 2

```js
// Node.js program to demonstrate the
// util.types.isUint8ClampedArray() method

// Import the util module
const util = require('util');

// Checking a big unsigned 64-bit
// integer array
let UintClampedArr = 
    new Uint8ClampedArray([0, 128, 1024, 2054]);

console.log(UintClampedArr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(UintClampedArr);

console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);

// Checking a unsigned 32-bit integer array
let unsigned32Arr = new Uint32Array([4, 25, 128]);
console.log(unsigned32Arr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(unsigned32Arr);
console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);

// Checking a big signed 64-bit integer array
let bigSigned64Arr = new BigInt64Array([16n, 25n, 128n]);
console.log(bigSigned64Arr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(bigSigned64Arr);
console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);
```

**输出：**

```js
Uint8ClampedArray [ 0, 128, 255, 255 ]
Object is Unsigned 8-bit clamped array object: true
Uint32Array [ 4, 25, 128 ]
Object is Unsigned 8-bit clamped array object: false
BigInt64Array [ 16n, 25n, 128n ]
Object is Unsigned 8-bit clamped array object: false
```

**参考：**[https://nodejs.org/api/util.html#util_util_types_isuint8clampedarray_value](https://nodejs.org/api/util.html#util_util_types_isuint8clampedarray_value)