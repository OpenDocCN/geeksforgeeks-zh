# Node.js 流可写.destroyed 属性

> 原文：[https://www.geeksforgeeks.org/node-js-stream-writable-destroyed-property/](https://www.geeksforgeeks.org/node-js-stream-writable-destroyed-property/)

`writable.destroyed` 属性是 `stream` 模块的内置 API，用于检查 `writable.destroy()` 方法是否被调用。

## 语法

```js
writable.destroyed
```

## 返回值

如果在调用 `destroy()` 方法之后调用了该属性，则该属性返回 `true`，否则返回 `false`。

下面的例子说明了在 Node.js 中 `writable.destroyed` 属性的使用：

## 例 1

```js
// Node.js program to demonstrate the
// writable.destroyed Property

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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('hello');

// Calling destroy function
writable.destroy();

// Calling the Property
writable.destroyed;
```

## 输出

```js
hi
hello
true
```

## 例 2

```js
// Node.js program to demonstrate the
// writable.destroyed Property

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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('hello');

// Calling the Property
writable.destroyed;
```

## 输出

```js
hi
hello
false
```

在上面的示例中，输出为 `false`，因为在调用属性 `writable.destroyed` 之前没有调用 `writable.destroy()` 方法。

## 参考

[https://nodejs.org/api/stream.html#stream_writable_destroyed](https://nodejs.org/api/stream.html#stream_writable_destroyed)