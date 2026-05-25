# Node.js 中 readFile 和 createReadStream 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-readfile-and-createreadstream-in-node-js/](https://www.geeksforgeeks.org/difference-between-readfile-and-createreadstream-in-node-js/)

在本文中，我们将讨论 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 中 `readFile` 和 `createReadStream` 的区别。这两个模块都允许我们打开文件/流并读取其中的数据。

## readFile

`fs` 模块包含 `readFile` 方法。它用于通过将文件放入缓冲区来读取文件。这是一个异步方法，因此，它读取文件时不会阻止代码的执行。首先，我们将 `fs` 模块引入我们的应用程序，然后在其中使用 `readFile` 方法。

**语法:**

```js
fs.readFile( filename, encoding, callback_function)
```

**参数:**

*   **filename:** 保存要读取的文件的路径。
*   **encoding:** 保存文件的编码。如果未指定选项，则返回原始缓冲区，默认值为 `"utf8"`。
*   **callback_function:** 是读取文件后被调用的函数，包含两个参数 `err` 和 `data`。如果遇到任何错误，那么它会存储在 `err` 中，否则文件的内容会存储在 `data` 中。

**返回值:** 返回文件的内容。

**示例:** 在本例中，我们使用 `readFile` 方法读取文件，要读取的文件是 `output.txt`。

**output.txt 文件:**

```js
This is an output file read from readFile method.
```

**index.js**

```js
const fs = require('fs');
fs.readFile('output.txt', 'utf8', (err, data) => {
  console.log(`Data present in the file is::    ${data}`);
});
console.log('Outside readFile method');
```

**输出:**

```js
Outside readFile method
Data present in the file is::   
This is an output file read from readFile method.
```

## createReadStream

`fs` 模块包含内置的 API（应用编程接口）`createReadStream`。它允许我们打开一个文件/流并读取其中的数据。

**语法:**

```js
fs.createReadStream(path, options)
```

**参数:**

*   **path:** 保存需要读取的文件路径。它可能是字符串，缓冲区的网址。
*   **options:** 为可选参数。我们可以传递一个字符串或对象给它。

**返回值:** 返回 `ReadStream` 对象。

**示例:** 在本例中，我们通过 `createReadStream.on` 方法读取文件名 `output.txt`。

**output.txt 文件:**

```js
This is an output file read from createReadStream method.
```

**index.js**

```js
const fs = require('fs');
const createReader = fs.createReadStream('output.txt');

createReader.on('data', (data) => {
  console.log(data.toString());
});

console.log('Outside createReader.on method');
```

**输出:**

```js
Outside createReader.on method
This is an output file read from createReadStream method.
```

## readFile 与 createReadStream 的区别

| readFile | createReadStream |
| :--- | :--- |
| 它先将文件读入内存，然后将文件提供给用户。 | 根据用户需要，以块（chunk）为单位读取文件。 |
| 读取整个文件速度较慢。 | 因为它具有分块传输的属性，所以速度更快。 |
| 它不会在请求太多的情况下扩展，因为它会尝试同时加载它们。 | 它是可伸缩的，因为它将内容直接管道传输到 HTTP 响应对象。 |
| 由于其属性，Node.js 在这种情况下更容易处理内存清理。 | 在这种情况下，通过 Node.js 不容易清理内存。 |