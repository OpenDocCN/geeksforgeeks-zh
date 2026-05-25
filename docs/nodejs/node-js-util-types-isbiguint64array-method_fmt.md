# Node.js util.types.isBigUint64Array()方法

> 原文: [https://www.geeksforgeeks.org/node-js-util-types-isbiguint64array-method/](https://www.geeksforgeeks.org/node-js-util-types-isbiguint64array-method/)

`util`模块的`util.types.isBigUint64Array()`方法主要是为了支持Node.js自带的内部API的需求而设计的。

`util.types.isBigUint64Array()`方法用于检查给定值是否为`BigUint64Array`对象。

## 语法

```js
util.types.isBigUint64Array( value )
```

## 参数

该函数接受一个参数，如上所述，如下所述:

*   `value`: This is the value to be checked for the `BigUint64Array` object.

## 返回值

如果传递的值是`BigUint64Array`的实例，该方法返回一个布尔值，即`true`，否则返回`false`。

下面的例子说明了Node.js中的`util.types.isBigUint64Array()`方法:

## 例 1

```js
// Node.js program to demonstrate the     
// util.types.isBigUint64Array() method

// Import the util module
const util = require('util');

// Checking for a big signed 64-bit integer array
isBigUnsignedint64Arr
  = util.types.isBigUint64Array(new BigUint64Array());
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);

isBigUnsignedint64Arr
  = util.types.isBigUint64Array(new BigInt64Array());
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);

isBigUnsignedint64Arr
  = util.types.isBigUint64Array(new Int32Array());
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);
```

**输出:**

```js
Object is Big Unsigned 64-bit array object: true
Object is Big Unsigned 64-bit array object: false
Object is Big Unsigned 64-bit array object: false
```

## 例 2

```js
// Node.js program to demonstrate the     
// util.types.isBigUint64Array() method

// Import the util module
const util = require('util');

// Checking a big unsigned 64-bit integer array
let bigUnsigned64Arr
  = new BigUint64Array([16n, 25n, 69n]);
console.log(bigUnsigned64Arr);

isBigUnsignedint64Arr
  = util.types.isBigUint64Array(bigUnsigned64Arr);
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);

// Checking a big signed 64-bit integer array
let bigSigned64Arr
  = new BigInt64Array([16n, 25n, 69n]);
console.log(bigSigned64Arr);

isBigUnsignedint64Arr
  = util.types.isBigUint64Array(bigSigned64Arr);
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);

// Checking a unsigned 32-bit integer array
let unsigned32Arr
  = new Uint32Array([16, 25, 69]);
console.log(unsigned32Arr);

isBigUnsignedint64Arr
  = util.types.isBigUint64Array(unsigned32Arr);
console.log("Object is Big Unsigned 64-bit array object:",
  isBigUnsignedint64Arr);
```

**输出:**

```js
BigUint64Array [ 16n, 25n, 69n ]
Object is Big Unsigned 64-bit array object: true
BigInt64Array [ 16n, 25n, 69n ]
Object is Big Unsigned 64-bit array object: false
Uint32Array [ 16, 25, 69 ]
Object is Big Unsigned 64-bit array object: false
```

**参考:** [https://nodejs.org/api/util.html#util_util_types_isbiguint64array_value](https://nodejs.org/api/util.html#util_util_types_isbiguint64array_value)