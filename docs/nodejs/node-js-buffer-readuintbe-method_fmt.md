# Node.js Buffer.readUIntBE()方法

> 原文: [https://www.geeksforgeeks.org/node-js-buffer-readuintbe-method/](https://www.geeksforgeeks.org/node-js-buffer-readuintbe-method/)

`Buffer.readUIntBE()`方法是`Buffer`模块中类`Buffer`的内置应用编程接口，用于从指定偏移量处的已分配缓冲区中读取指定数量的字节值。

## 语法

```js
Buffer.readUIntBE( offset, byteLength )
```

## 参数

该方法接受两个参数，如下所述：

*   `offset`：指定读取前要跳过的字节数，或者简单地表示缓冲区中的索引。`offset`的值必须满足 **0 <= offset <= buffer.length - byteLength**。其默认值为 0。
*   `byteLength`：指定要读取的字节数。`byteLength`的值必须满足 **0 < byteLength <= 6**。

## 返回值

这个方法返回一个从缓冲区读取的大端格式的整数值。

下面的例子说明了在 Node.js 中使用`Buffer.readUIntBE()`方法：

## 例 1

```js
// Node program to demonstrate the
// Buffer.readUIntBE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading data from the buffer
// and printing it as a string
console.log(buf.readUIntBE(0, 3).toString(16));
console.log(buf.readUIntBE(1, 3).toString(16));
console.log(buf.readUIntBE(2, 2).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
```

## 例 2

```js
// Node program to demonstrate the
// Buffer.readUIntBE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading data from the buffer
// and printing it as a string
console.log(buf.readUIntBE(0, 3).toString(16));
console.log(buf.readUIntLE(0, 3).toString(16));
console.log(buf.readUIntBE(1, 2).toString(16));
console.log(buf.readUIntLE(1, 2).toString(16));
console.log(buf.readUIntBE(2, 1).toString(16));
console.log(buf.readUIntLE(2, 1).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
```

## 例 3

```js
// Node program to demonstrate the
// Buffer.readUIntBE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading data from the buffer
// and printing it as a string
console.log(buf.readUIntBE(0, 4).toString(16));
console.log(buf.readUIntBE(1, 2).toString(16));
console.log(buf.readUIntBE(2, 3).toString(16));

// Wrong index is provided to produce error
console.log(buf.readUIntBE(3, 6).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>

internal/buffer.js:49
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 1. Received 2
    at boundsError (internal/buffer.js:49:9)
    at readUInt24BE (internal/buffer.js:205:5)
    at Buffer.readUIntBE (internal/buffer.js:148:12)
    . . .
```

## 注意

以上程序使用`node index.js`命令编译运行。

## 参考

[https://nodejs.org/api/buffer.html#buffer_buf_readuintbe_offset_bytelength](https://nodejs.org/api/buffer.html#buffer_buf_readuintbe_offset_bytelength)