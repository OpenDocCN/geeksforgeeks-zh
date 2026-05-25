# Node.js Stream 可写流 `cork()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stream-writable-cork-method/](https://www.geeksforgeeks.org/node-js-stream-writable-cork-method/)

`writable.cork()` 方法是 `Stream` 模块的内置 API，用于将每个写入的数据暂存到缓冲区中。当我们调用 `stream.uncork()` 或 `stream.end()` 方法时，缓冲区中的数据才会被刷新（输出）。

## 语法

```js
writable.cork()
```

## 参数

此方法不接受任何参数。

## 返回值

如果使用此方法，则在此方法之后写入的数据不会立即显示在输出中，因为这些数据被存储在内存中，直到调用 `uncork()` 或 `end()` 方法才会输出。

## 示例

以下示例说明了 Node.js 中 `writable.cork()` 方法的使用：

### 示例 1

```js
// Node.js program to demonstrate the
// writable.cork() method
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

// Writing data
writable.write('hi');

// Calling cork() function
writable.cork();

// Again writing some data
writable.write('hello');
writable.write('world');
```

**输出：**

```js
hi
true
```

在上面的例子中，仅显示了在 `cork()` 方法之前写入的数据。在其被 `cork()` 之后写入的数据，即存储在内存中，没有被输出。

### 示例 2

```js
// Node.js program to demonstrate the
// writable.cork() method
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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('hello');
writable.write('world');

// Calling cork() function
writable.cork();
```

**输出：**

```js
hi
hello
world
```

在上面的例子中，`cork()` 方法在最后被调用，因此没有任何数据被存储在内存中。所有写入的数据都会立即显示在输出中。

## 参考

[https://nodejs.org/api/stream.html#stream_writable_cork](https://nodejs.org/api/stream.html#stream_writable_cork)