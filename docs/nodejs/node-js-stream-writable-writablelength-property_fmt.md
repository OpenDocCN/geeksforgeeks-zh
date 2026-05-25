# Node.js Stream 可写流的 writableLength 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stream-writable-writablelength-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writablelength-property/)

`writable.writableLength` 属性是 `stream` 模块的内置应用，用于检查队列中准备写入的字节数。

## 语法

```js
writable.writableLength
```

## 返回值

该属性返回准备写入队列的字节数。

下面的例子说明了在 Node.js 中 `writable.writableLength` 属性的使用：

## 例 1

```js
// Node.js program to demonstrate the     
// writable.writableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

// Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

// Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Calling cork() function
writable.cork();

//Writing data
writable.write('hi');

// Again writing some data
writable.write('GFG');

// Calling writable.writableLength 
// Property
writable.writableLength;
```

**输出：**

```js

```

## 例 2

```js
// Node.js program to demonstrate the     
// writable.writableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

// Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

// Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Calling cork() function
writable.cork();

//Writing data
writable.write('hi');

// Calling uncork() function
writable.uncork();

// Again calling cork function
writable.cork();

// Again writing some data
writable.write('GFG');

// Calling writable.writableLength 
// Property
writable.writableLength;
```

**输出：**

```js
hi

```

这里，数据“hi”不再存在于缓冲器中，因此，缓冲器只有 3 个字节存在，数据“GFG”需要 3 个字节。

**参考：**[https://nodejs.org/api/stream.html#stream_writable_writablelength](https://nodejs.org/api/stream.html#stream_writable_writablelength)