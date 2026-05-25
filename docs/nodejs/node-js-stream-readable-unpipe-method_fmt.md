# Node.js Stream 可读流 `unpipe()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stream-readable-unpipe-method/](https://www.geeksforgeeks.org/node-js-stream-readable-unpipe-method/)

可读流中的 `unpipe()` 方法用于分离之前在使用 `stream.pipe()` 方法时附加的可写流。

## 语法：

```js
readable.unpipe( destination )
```

## 参数：
该方法接受单参数 `destination`，即待分离的可写流的目的地。

## 返回值：
返回流。可写，即目的地。

以下示例说明了在 Node.js 中使用 `unpipe()` 方法：

### 例 1：

```js
// Node.js program to demonstrate the     
// readable.unpipe() method

// Accessing fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable Stream
const writable = fs.createWriteStream("output.text");

// Calling pipe method
readable.pipe(writable);

// Calling unpipe method
readable.unpipe(writable);
console.log("done");
```

### 输出：

```js
done
```

### 例 2：

```js
// Node.js program to demonstrate the     
// readable.unpipe() method

// Accessing fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable Stream
const writable = fs.createWriteStream("output.text");

// All the data from readable goes into 'output.text',
// for only two seconds.
readable.pipe(writable);
setTimeout(() => {
  console.log('Stop writing to output.text.');

// Calling unpipe method
  readable.unpipe(writable);
  console.log('close the file stream.');

//Calling end method
  writable.end();
}, 2000);
console.log("done");
```

### 输出：

```js
done
Stop writing to output.text.
close the file stream.
```

参考：[https://nodejs.org/api/stream.html#stream_readable_unpipe_destination](https://nodejs.org/api/stream.html#stream_readable_unpipe_destination)。