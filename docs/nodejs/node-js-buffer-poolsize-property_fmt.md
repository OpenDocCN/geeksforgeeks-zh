# Node.js Buffer.poolSize 属性

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-poolsize-property/](https://www.geeksforgeeks.org/node-js-buffer-poolsize-property/)

`Buffer.poolSize` 属性是一个内置的应用程序编程接口类 `Buffer`，带有 in Buffer 模块，它给出了用于池化的预分配内部 `Buffer` 实例的大小（以字节为单位）。该值可以修改。

**语法：**

```js
Buffer.poolSize = value
```

**返回值：** 返回用于池化的内部缓冲区实例的大小。

**例 1：**

```js
// Node.js program to demonstrate the
// Buffer.poolSize property

// Assign the poolsize to the buffer
Buffer.poolSize = 1024;

// Display the buffer poolsize
console.log(Buffer.poolSize);
```

**输出：**

```js

```

**例 2：**

```js
// Node.js program to demonstrate the
// Buffer.poolSize property

// Display the default buffer poolsize
console.log(Buffer.poolSize);
```

**输出：**

```js

```

**参考：** [https://nodejs.org/api/buffer.html#buffer_class_property_buffer_poolsize](https://nodejs.org/api/buffer.html#buffer_class_property_buffer_poolsize)