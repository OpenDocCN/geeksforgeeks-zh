# Node.js zlib.brotliCompressSync() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-zlib-brotlicompresssync-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlicompresssync-method/)

`zlib.brotliCompressSync()` 方法是 Zlib 模块的内置应用编程接口，用于使用 BrotliCompress 压缩一大块数据。

## 语法

```js
zlib.brotliCompressSync( buffer, options )
```

## 参数

该方法接受两个参数，如下所述：

*   `buffer`: 一个 `Buffer`、`TypedArray`、`DataView`、`ArrayBuffer` 或字符串。
*   `options`: 一个可选参数。

## 返回值

用 BrotliCompress 返回数据块。

## 示例

以下示例说明了在 Node.js 中使用 `zlib.brotliCompressSync()` 方法：

### 例 1

```js
// Node.js program to demonstrate the     
// zlib.brotliCompressSync() method

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "0123456789";

// Calling brotliCompressSync method
var brotliCom = zlib.brotliCompressSync(input);

console.log(brotliCom);
```

**输出:**

```js
// Buffer 8b 04 80 30 31 32 33 34 35 36 37 38 39 03
```

### 例 2

```js
// Node.js program to demonstrate the     
// zlib.brotliCompressSync() method

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "0123456789";

// Calling brotliCompressSync method
var brotliCom = zlib.brotliCompressSync(input).toString('hex');

console.log(brotliCom);
```

**输出:**

```js
8b04803031323334353637383903
```

## 参考资料

[https://nodejs.org/api/zlib.html#zlib_zlib_brotlicompresssync_buffer_options](https://nodejs.org/api/zlib.html#zlib_zlib_brotlicompresssync_buffer_options)