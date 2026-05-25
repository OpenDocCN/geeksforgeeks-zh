# Node.js 流 readable.destroyed 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stream-readable-destroyed-property/](https://www.geeksforgeeks.org/node-js-stream-readable-destroyed-property/)

`readable.destroyed`属性是 Stream 模块的内置 API，用于检查`readable.destroy()`函数是否被调用。

## 语法：

```js
readable.destroyed
```

## 返回值：
如果可读流已被销毁则返回`true`，否则返回`false`。

下面的例子说明了在 Node.js 中`readable.destroyed`属性的使用：

## 例 1：

```js
// Node.js program to demonstrate the     
// readable.destroyed Property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

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

// Handling error event
readable.on('error', err => {
    console.log(err);
});

// Calling destroy method
// with parameter
readable.destroy('error');

// Displays that the stream is 
// destroyed
console.log("Stream destroyed");

// Calling readable.destroyed
// Property
readable.destroyed;
```

## 输出：

```js
Stream destroyed
true
error
```

## 例 2：

```js
// Node.js program to demonstrate the     
// readable.destroyed Property

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

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

// Displays that the stream is 
// destroyed
console.log("Program completed!!");

// Calling readable.destroyed
// Property
readable.destroyed;
```

## 输出：

```js
Program completed!!
false
read: hello
```

所以，这里`readable.destroy()`方法在`readable.destroyed`属性之前不被调用，所以它返回`false`。

## 参考：
[https://nodejs.org/api/stream.html#stream_readable_destroyed](https://nodejs.org/api/stream.html#stream_readable_destroyed)