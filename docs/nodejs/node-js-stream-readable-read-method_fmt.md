# Node.js Stream `readable.read()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-stream-readable-read-method/](https://www.geeksforgeeks.org/node-js-stream-readable-read-method/)

`readable.read()` 方法是 Stream 模块的内置 API，用于从内部缓冲区中读取数据。如果没有指定编码或者流在对象模式下工作，它将数据作为 Buffer 对象返回。

## 语法:
```js
readable.read( size )
```

## 参数:
该方法接受单个参数 `size`，指定从内部缓冲区读取的字节数。

## 返回值:
如果指定了 `size` 参数，则返回该数量的字节数据。如果缓冲区中不存在足够的数据，则返回 `null`。

下面的例子说明了在 Node.js 中 `readable.read()` 方法的使用:

## 例 1:
```js
// Node.js program to demonstrate the
// readable.read() method

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

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});
console.log("done");
```

## 输出:
```js
done
read: hello
```

这里，在上面的例子中，从缓冲区读取的数据是“hello”，所以它被返回。

## 例 2:
```js
// Node.js program to demonstrate the
// readable.read() method

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read(1))) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});
console.log("done");
```

## 输出:
```js
done
read: h
read: e
read: l
read: l
read: o
```

在上面的例子中，说明了数据的大小，因此在每个步骤中只从包含数据“hello”的文件“input.txt”中读取一个字节。

## 参考:
[https://nodejs.org/api/stream.html#stream_readable_read_size](https://nodejs.org/api/stream.html#stream_readable_read_size)