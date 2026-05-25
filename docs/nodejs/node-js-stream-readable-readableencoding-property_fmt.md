# Node.js Stream 可读流 `readableEncoding` 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stream-readable-readableencoding-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readableencoding-property/)

可读流中的 `readable.readableEncoding` 属性用于获取所述可读流的属性编码。此外，您可以使用 `readable.setEncoding()` 方法设置此属性。

## 语法：

```js
readable.readableEncoding
```

## 返回值：
返回程序中使用的编码。

下面的例子说明了在 Node.js 中 `readable.readableEncoding` 属性的使用：

## 例 1：

```js
// Node.js program to demonstrate the     
// readable.readableEncoding Property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Setting the encoding 
readable.setEncoding("base64");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

// Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read())) {

// Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readableEncoding property
readable.readableEncoding;
```

## 输出：

```js
read: aGVs
read: bG8=
```

## 例 2：

```js
// Node.js program to demonstrate the     
// readable.readableEncoding Property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Setting the encoding 
readable.setEncoding("hex");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

// Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read())) {

// Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readableEncoding property
readable.readableEncoding;
```

## 输出：

```js
read: 68656c6c6f
```

## 参考：
[https://nodejs.org/api/stream.html#stream_readable_readableencoding](https://nodejs.org/api/stream.html#stream_readable_readableencoding)。