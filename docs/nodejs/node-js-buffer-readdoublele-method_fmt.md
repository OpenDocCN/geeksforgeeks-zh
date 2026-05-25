# Node.js Buffer.readDoubleLE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-readdoublele-method/](https://www.geeksforgeeks.org/node-js-buffer-readdoublele-method/)

Node.js 中的`Buffer.readDoubleLE()`方法用于以小端格式从给定偏移量的缓冲区中读取 64 位双精度值。

**语法：**

```js
Buffer.readDoubleLE(offset)
```

**参数：** 该方法接受单参数`offset`，该偏移量保存开始读取前要跳过的字节数。偏移值介于 `0 <= offset <= buf.length - 8` 之间。其默认值为 0。

**返回值：** 返回小端格式的整数值。

下面的例子说明了`buf.readDoubleLE()`方法在 Node.js 中的使用：

**例 1：**

```js
// Node program to demonstrate the
// Buffer.readDoubleLE() method

// Creating a buffer of given size
const buf = Buffer.from([1, 2, 3, 4, 5, 6, 7, 8]);

// Display the result
console.log(buf.readDoubleLE(0));
console.log(buf);
```

**输出：**

```js
5.447603722011605e-270
<Buffer 01 02 03 04 05 06 07 08>
```

**例 2：**

```js
// Node program to demonstrate the
// Buffer.readDoubleBE() method

// Creating a buffer of given size
const buf = Buffer.from([11, 22, 33, 44, 55, 66, 77, 88]);

// Display the result
console.log("Functions of Buffer.readDoubleLE(int)");
console.log(buf.readDoubleLE(55));
console.log(buf);
```

**输出：**

```js
Functions of Buffer.readDoubleLE(int)
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 55. Received <received>
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_buf_readdouble_offset](https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_buf_readdouble_offset)