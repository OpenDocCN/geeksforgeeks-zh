# Node.js zlib.inflateRaw() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-zlib-inflateraw-method/](https://www.geeksforgeeks.org/node-js-zlib-inflateraw-method/)

`zlib.inflateRaw()` 方法是 `zlib` 模块的一个内置应用编程接口，用于解压缩一大块数据。

## 语法

```js
zlib.inflateRaw( buffer, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   `buffer`：可以是 `Buffer`、`TypedArray`、`DataView`、`ArrayBuffer` 和 `string` 类型。
*   `options`：是一个可选参数，用于保存 `zlib` 选项。
*   `callback`：持有回调函数。

## 返回值

解压后返回数据块。

## 示例

以下示例说明了在 Node.js 中使用 `zlib.inflateRaw()` 方法：

### 例 1

```js
// Node.js program to demonstrate the
// inflateRaw() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "GeeksforGeeks";

// Calling deflateRaw method
zlib.deflateRaw(input, (err, buffer) => {

  // Calling inflateRaw
  zlib.inflateRaw(buffer, (err, buffer) => {
    console.log(buffer.toString('utf8'));
  });
});
```

**输出:**

```js
GeeksforGeeks
```

### 例 2

```js
// Node.js program to demonstrate the
// inflateRaw() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "GeeksforGeeks";

// Calling deflateRaw method
zlib.deflateRaw(input, (err, buffer) => {

  // Calling inflateRaw
  zlib.inflateRaw(buffer, (err, buffer) => {
    console.log(buffer.toString('base64'));
  });
});
```

**输出:**

```js
R2Vla3Nmb3JHZWVrcw==
```

## 参考

[https://nodejs.org/api/zlib.html#zlib_zlib_inflateraw_buffer_options_callback](https://nodejs.org/api/zlib.html#zlib_zlib_inflateraw_buffer_options_callback)