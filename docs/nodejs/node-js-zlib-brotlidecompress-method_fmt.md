# Node.js zlib.brotliDecompress()方法

> 原文：[https://www.geeksforgeeks.org/node-js-zlib-brotlidecompress-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlidecompress-method/)

`zlib.brotliDecompress()`方法是`zlib`模块的内置应用程序编程接口，用于使用brotliDecompress解压缩一大块数据。

## 语法

```js
zlib.brotliDecompress( buffer, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   `buffer`：可以是`Buffer`、`TypedArray`、`DataView`、`ArrayBuffer`和`string`类型。
*   `option`：可选参数，用于保存`zlib`选项。
*   `callback`：持有回调函数。

## 返回值

解压后返回数据块。

## 示例说明

以下示例说明了在Node.js中使用`zlib.brotliDecompress()`方法：

### 示例 1

```js
// Node.js program to demonstrate the     
// brotliDecompress() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Computer Science";

// Calling brotliCompress method
zlib.brotliCompress(input, (err, buffer) => {

// Calling brotliDecompress
    zlib.brotliDecompress(buffer, (err, buffer) => {
        console.log(buffer.toString('base64'));
    });
});
```

#### 输出

```js
Q29tcHV0ZXIgU2NpZW5jZQ== 
```

### 示例 2

```js
// Node.js program to demonstrate the     
// brotliDecompress() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Computer Science";

// Calling brotliCompress method
zlib.brotliCompress(input, (err, buffer) => {

// Calling brotliDecompress
    zlib.brotliDecompress(buffer, (err, buffer) => {
        console.log(buffer.toString('bas64'));
    });
});
```

#### 输出

```js
buffer.js:631  throw new ERR_UNKNOWN_ENCODING(encoding);  ^

TypeError [ERR_UNKNOWN_ENCODING]: Unknown encoding: bas64
    at stringSlice (buffer.js:631:9)    at Buffer.toString (buffer.js:667:10)
    at BrotliDecompress.zlib.brotliDecompress [as cb] 
    (/home/runner/BeautifulMiserlySourcecode/index.js:18:28)
    at BrotliDecompress.zlibBufferOnEnd (zlib.js:133:10)
    at BrotliDecompress.emit (events.js:203:15)
    at BrotliDecompress.EventEmitter.emit (domain.js:448:20)
    at endReadableNT (_stream_readable.js:1143:12)
    at process._tickCallback (internal/process/next_tick.js:63:19)? 
```

在这里，编码时发生错误，因此会引发错误。

## 参考

[https://nodejs.org/api/zlib.html#zlib_zlib_brotlidecompress_buffer_options_callback](https://nodejs.org/api/zlib.html#zlib_zlib_brotlidecompress_buffer_options_callback)