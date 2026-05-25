# Node.js Stream `readable.readableLength` 属性

> 原文：`https://www.geeksforgeeks.org/node-js-stream-readable-readablelength-property/`

可读流中的 `readable.readableLength` 属性，用于检查队列中准备读取的字节数。

## 语法

```js
readable.readableLength
```

## 返回值

返回队列中准备读取的字节数。

## 例子

下面的例子说明了在 Node.js 中 `readable.readableLength` 属性的使用：

### 例 1

```js
// Node.js program to demonstrate the     
// readable.readableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a Readable stream 
const readable = new stream.Readable("input.txt");

// Calling readable.readableLength 
// Property
readable.readableLength;
```

**输出：**

```js

```

### 例 2

```js
// Node.js program to demonstrate the     
// readable.readableLength property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

// Using while loop and calling
  // read method
  while (null !== (chunk = readable.read())) {

// Displaying the chunk length
    console.log(`read: ${chunk.length}`);
     }
});

// Calling readableLength property
readable.readableLength;
```

**输出：**

```js

read: 13

```

**参考：** `https://nodejs.org/api/stream.html#stream_readable_readablelength`。