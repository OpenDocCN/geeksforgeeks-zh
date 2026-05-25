# Node.js zlib.unzip()方法

> 原文：`https://www.geeksforgeeks.org/node-js-zlib-unzip-method/`

`zlib.unzip()`方法是`zlib`模块的内置应用程序编程接口，用于解压缩一大块数据。

## 语法

```js
zlib.unzip( buffer, options, callback )
```

## 参数

该方法接受三个参数，如上所述，如下所述：

*   `Buffer`：它可以是`buffer`、`type`、`data view`、`array buffer`和`string`类型。
*   `option`：这是一个用于保存`zlib`选项的可选参数。
*   `Callback`：它持有回调函数。

## 返回值

解压后返回数据块。

下面的例子说明了在Node.js中使用`zlib.unzip()`方法：

## 例 1

```js
// Node.js program to demonstrate the unzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning it a value string
var input = "GfG";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

    // Calling unzip method
    zlib.unzip(buffer, (err, buffer) => {

        console.log(buffer.toString('utf8'));

    });
});

console.log("Data Decompressed...");
```

## 输出

```js
Data Decompressed...
GfG
```

## 例 2

```js
// Node.js program to demonstrate the unzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning it a value string
var input = "GfG";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

    // Calling unzip method
    zlib.unzip(buffer, (err, buffer) => {

        console.log(buffer.toString('base64'));

    });
});

console.log("Data Decompressed...");
```

## 输出

```js
Data Decompressed...
R2ZH
```

## 参考

[`https://nodejs.org/api/zlib.html#zlib_zlib_unzip_buffer_options_callback`](https://nodejs.org/api/zlib.html#zlib_zlib_unzip_buffer_options_callback)