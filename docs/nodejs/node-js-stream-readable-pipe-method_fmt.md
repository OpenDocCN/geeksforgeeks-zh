# Node.js Stream 可读流 `pipe()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stream-readable-pipe-method/](https://www.geeksforgeeks.org/node-js-stream-readable-pipe-method/)

可读流中的 `pipe()` 方法用于将可写流附加到可读流，从而切换到流动模式，然后将其拥有的所有数据推送到附加的可写流。

## 语法

```js
readable.pipe( destination, options )
```

## 参数

该方法接受两个参数，如下所述：

*   **`destination`**：此参数存储写入数据的目标。
*   **`options`**：此参数存储管道选项。

## 返回值

返回目标可写流。如果是双工或转换流，则允许管道链。

下面的例子说明了在 Node.js 中使用 `pipe()` 方法：

## 例 1

```js
// Node.js program to demonstrate the
// readable.pipe() method

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Calling pipe method
readable.pipe(writable);

console.log("Program Ended");
```

**输出：**

```js
Program Ended
```

因此，在管道方法之后，名为 `output.txt` 的文件必须包含文件 `input.txt` 中的数据。

## 例 2

```js
// Node.js program to demonstrate
// the chaining of streams using
// readable.pipe() method

// Accessing fs and zlib module
var fs = require("fs");
var zlib = require('zlib');

// Compress the file input.txt to
// input.txt.gz using pipe() method
fs.createReadStream('input.txt')
   .pipe(zlib.createGzip())
   .pipe(fs.createWriteStream('input.txt.gz'));

console.log("File Compressed.");
```

**输出：**

```js
File Compressed.
```

**参考：**[https://nodejs.org/api/stream.html#stream_readable_pipe_destination_options](https://nodejs.org/api/stream.html#stream_readable_pipe_destination_options)。