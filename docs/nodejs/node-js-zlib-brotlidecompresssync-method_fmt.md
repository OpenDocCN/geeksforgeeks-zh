## `zlib.brotliDecompressSync()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-zlib-brotlidecompresssync-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlidecompresssync-method/)

`zlib.brotliDecompressSync()` 方法是 `zlib` 模块的内置应用程序编程接口，用于使用 BrotliDecompress 解压缩数据块。

### 语法

```js
zlib.brotliDecompressSync( buffer, options )
```

### 参数

该方法接受两个参数：

*   `buffer`：`Buffer`、`TypedArray`、`DataView`、`ArrayBuffer` 或字符串，包含要解压缩的数据。
*   `options`：此参数存储 `zlib` 选项值。

### 返回值

使用 BrotliDecompress 返回解压后的数据块。

### 示例

以下示例说明了在 Node.js 中使用 `zlib.brotliDecompressSync()` 方法：

**例 1：**

```js
// Node.js program to demonstrate the
// zlib.brotliDecompressSync() method

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var brotliCom = zlib.brotliCompressSync(input);
var brotliDec = zlib.brotliDecompressSync(
    new Buffer.from(brotliCom)).toString('hex');

console.log(brotliDec);
```

**输出：**

```js
4e69646869
```

**例 2：**

```js
// Node.js program to demonstrate the
// zlib.brotliDecompressSync() method

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var brotliCom = zlib.brotliCompressSync(input).toString('hex')
var brotliDec = zlib.brotliDecompressSync(
    new Buffer.from(brotliCom, 'hex')).toString('base64');

console.log(brotliDec);
```

**输出：**

```js
TmlkaGk=
```

### 参考

[https://nodejs.org/api/zlib.html#zlib_zlib_brotlidecompresssync_buffer_options](https://nodejs.org/api/zlib.html#zlib_zlib_brotlidecompresssync_buffer_options)