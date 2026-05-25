# Node.js `fs.createReadStream()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-createreadstream-method/](https://www.geeksforgeeks.org/node-js-fs-createreadstream-method/)

`createReadStream()`方法是`fs`模块的内置应用编程接口，允许您打开文件/流并读取其中存在的数据。

**语法:**
```js
fs.createReadStream( path, options )
```

**参数:** 该方法接受两个参数，如上所述，如下所述:
*   `path`: 此参数保存读取文件的文件路径。它可以是字符串、缓冲区或网址。
*   `options`: 是保存字符串或对象的可选参数。

**返回值:** 该方法返回`fs.ReadStream`对象。

以下示例说明了 Node.js 中的`createReadStream()`方法。

### 示例 1
```js
// Node.js program to demonstrate the 
// fs.createReadStream() method

// Include fs module
let fs = require('fs'),

// Use fs.createReadStream() method
// to read the file
reader = fs.createReadStream('input.txt');

// Read and display the file data on console
reader.on('data', function (chunk) {
    console.log(chunk.toString());
});
```

**输出:**
```js
input.txt file data:
GeeksforGeeks: A computer science portal for geeks
```

### 示例 2
```js
// Node.js program to demonstrate the 
// fs.createReadStream() method

// Include fs module
let fs = require('fs'),

// Use fs.createReadStream() method
// to read the file
reader = fs.createReadStream('input.txt', {
    flag: 'a+',
    encoding: 'UTF-8',
    start: 5,
    end: 64,
    highWaterMark: 16
});

// Read and display the file data on console
reader.on('data', function (chunk) {
    console.log(chunk);
});
```

**输出:**
```js
forGeeks: A comp
uter science por
tal for geeks
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_createreadstream_path_options](https://nodejs.org/api/fs.html#fs_fs_createreadstream_path_options)