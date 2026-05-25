# Node.js zlib.inflate() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-zlib-inflate-method/](https://www.geeksforgeeks.org/node-js-zlib-inflate-method/)

`zlib.inflate()` 方法是 `zlib` 模块的一个内置应用编程接口，用于解压缩一大块数据。

## 语法

```js
zlib.inflate( buffer, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   **buffer**: 可以是 `Buffer`、`TypedArray`、`DataView`、`ArrayBuffer` 和 `string` 类型。
*   **options**: 一个可选参数，用于保存 `zlib` 选项。
*   **callback**: 它持有回调函数。

## 返回值

解压后返回数据块。

## 示例

以下示例说明了在 Node.js 中使用 `zlib.inflate()` 方法：

### 示例 1

```js
// Node.js program to demonstrate the inflate() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning it a value string
var input = "Geeks";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {
  // Calling inflate method
  zlib.inflate(buffer, (err, buffer) => {
    console.log(buffer.toString('utf8'));
  });
});
```

**输出:**

```js
Geeks
```

### 示例 2

```js
// Node.js program to demonstrate the inflate() method

// Including zlib module
const zlib = require("zlib");

// Declare input and assign it a value string
var input = "Nidhi Singh";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {
  // Calling inflate method
  zlib.inflate(buffer, (err, buffer) => {
    console.log(buffer.toString('hex'));
  });
});
```

**输出:**

```js
4e696468692053696e6768
```

## 参考

[https://nodejs.org/api/zlib.html#zlib_zlib_inflate_buffer_options_callback](https://nodejs.org/api/zlib.html#zlib_zlib_inflate_buffer_options_callback)