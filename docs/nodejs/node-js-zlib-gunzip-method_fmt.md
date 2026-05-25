# Node.js `zlib.gunzip()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-zlib-gunzip-method/](https://www.geeksforgeeks.org/node-js-zlib-gunzip-method/)

`zlib.gunzip()`方法是`zlib`模块的内置应用程序编程接口，用于解压缩一大块数据。

## 语法

```js
zlib.gunzip( buffer, options, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   `buffer`：可以是`Buffer`、`TypedArray`、`DataView`、`ArrayBuffer`和`string`类型。
*   `option`：用于保存`zlib`选项的可选参数。
*   `callback`：持有的回调函数。

## 返回值

解压后返回数据块。

## 示例

以下示例说明了Node.js中`zlib.gunzip()`方法的使用：

### 例 1

```js
// Node.js program to demonstrate the gunzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling gunzip method
  zlib.gunzip(buffer, (err, buffer) => {
    console.log(buffer.toString('utf8'));
  });
});

console.log("Data Decompressed...");
```

**输出：**

```js
Data Decompressed...
Geek 
```

### 例 2

```js
// Node.js program to demonstrate the gunzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling gunzip method
  zlib.gunzip(buffer, (err, buffer) => {
    console.log(buffer.toString('hex'));
  });
});

console.log("Data Decompressed...");
```

**输出：**

```js
Data Decompressed...
4765656b 
```

## 参考

[https://nodejs.org/api/zlib.html#zlib_zlib_gunzip_buffer_options_callback](https://nodejs.org/api/zlib.html#zlib_zlib_gunzip_buffer_options_callback)