# Node.js util.types.isArrayBuffer() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-util-types-isarraybuffer-method/](https://www.geeksforgeeks.org/node-js-util-types-isarraybuffer-method/)

`util.types.isArrayBuffer()` 方法是 `util` 模块的内置 API，用于检查 Node.js 中的内置 `ArrayBuffer` 类型对象。

## 语法

```js
util.types.isArrayBuffer( value )
```

## 参数

该方法接受如上所述的单个参数，如下所述：

*   `value`：一个必需的参数，可以是任何数据类型。

## 返回值

返回一个布尔值，即如果该值是一个内置数组缓冲对象，则返回 `true`，否则返回 `false`。

下面的例子说明了 `util.types.isArrayBuffer()` 方法在 Node.js 中的使用：

## 示例 1

```js
// Node.js program to demonstrate the
// util.types.isArrayBuffer() Method

// Allocating util module
const util = require('util');

// Printing the returned value from
// util.types.isArrayBuffer() method
console.log(util.types.isArrayBuffer(new ArrayBuffer()));
console.log(util.types.isArrayBuffer(new SharedArrayBuffer()));
console.log(util.types.isArrayBuffer(39));
console.log(util.types.isArrayBuffer("gfg"));
```

**输出：**

```js
true
false
false
false
```

## 示例 2

```js
// Node.js program to demonstrate the
// util.types.isArrayBuffer() Method

// Allocating util module
const util = require('util');

// Printing the returned value from
// util.types.isArrayBuffer() method
if (util.types.isArrayBuffer(new ArrayBuffer())) {
    console.log("Passed value is built in ArrayBuffer");
}
if (util.types.isArrayBuffer(new SharedArrayBuffer())) {
    console.log("Passed value is built in ArrayBuffer");
}
```

**输出：**

```js
Passed value is built in ArrayBuffer
```

## 注意

以上程序使用 `node filename.js` 命令编译运行。

## 参考

[https://nodejs.org/api/util.html#util_util_types_isarraybuffer_value](https://nodejs.org/api/util.html#util_util_types_isarraybuffer_value)