# util.types.isTypedArray() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-istypedarray-method/](https://www.geeksforgeeks.org/node-js-util-types-istypedarray-method/)

`util.types.isTypedArray()` 方法是 `util` 模块的内置 API，主要是为了支持 `Node.js` 自身的内部 API 的需求而设计的。

`util.types.isTypedArray()` 方法用于确定该值是否是内置的 `TypedArray` 实例。

**语法：**

```js
util.types.isTypedArray( value )
```

**参数：** 该方法接受单个参数 `value`，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值：** 返回布尔值，即如果值是内置的 `TypedArray` 的实例，则返回 `true`，否则返回 `false`。

下面的例子说明了 `util.types.isTypedArray()` 方法在 Node.js 中的使用：

**例 1：**

```js
// Node.js program to demonstrate the
// util.types.isTypedArray() method

// Using require to access util module
const util = require('util');

// Using util.types.isTypedArray() method
console.log(util.types.isTypedArray(new ArrayBuffer()));

// Using util.types.isTypedArray() method
console.log(util.types.isTypedArray(new Uint8Array()));

// Using util.types.isTypedArray() method
console.log(util.types.isTypedArray(new Float64Array()));
```

**输出：**

```js
false
true
true
```

**例 2：**

```js
// Node.js program to demonstrate the
// util.types.isTypedArray() method

// Using require to access util module
const util = require('util');

// Using util.types.isTypedArray() method
console.log(util.types.isTypedArray([1, 5, 8, 18]));

// Using util.types.isTypedArray() method
console.log(util.types.isTypedArray(new Int8Array(8)));
```

**输出：**

```js
false
true
```

**注意：** 以上程序使用 `node index.js` 命令编译运行。

**参考：** [https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_istypedarray_value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_istypedarray_value)