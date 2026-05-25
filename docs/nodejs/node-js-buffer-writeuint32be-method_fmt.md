# Node.js Buffer.writeUInt32BE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-writeuint32be-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint32be-method/)

`Buffer.writeUInt32BE()`方法用于向`Buffer`类的实例中写入一个数字。该值以大端格式写入指定的偏移量。

## 语法

```js
buffer.writeUInt32BE(value, offset)
```

## 参数

此方法接受两个参数，如上所述，如下所述：

*   `value`：此参数保存要写入的数字。它应该是一个有效的无符号32位整数。此外，对于无效值没有定义行为。
*   `offset`：此参数存储要跳过的字节数。该值必须在范围 [0, `buffer.length`–4] 内。它是一个可选参数，默认值为零。

## 返回值

该方法返回写入字节数和偏移量之和。

## 例 1

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt32BE method

// Creating a buffer of size 8
const buffer = Buffer.allocUnsafe(8);

console.log(buffer);

// Return value is 4 
buffer.writeUInt32BE(0xabcdabcd, 0);

console.log(buffer);

// Return value is 8
buffer.writeUInt32BE(0xabcdabcd, 4);

console.log(buffer);
```

### 输出

```js
<Buffer 6c 69 63 65 00 00 00 00>
<Buffer ab cd ab cd 00 00 00 00>
<Buffer ab cd ab cd ab cd ab cd>
```

## 例 2

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt32BE method

// Creating a buffer of size 8
const buffer = Buffer.allocUnsafe(8);

console.log(buffer);

// Out of range error will be thrown
buffer.writeUInt32BE(0xabcdabcd, 5);
```

### 输出

```js
<Buffer b0 f1 67 fc 63 7f 00 00>
Thrown:
RangeError [ERR_OUT_OF_RANGE]  ........
```

## 参考

[https://nodejs.org/api/buffer.html#buffer_buf_readint32be_offset](https://nodejs.org/api/buffer.html#buffer_buf_readint32be_offset)