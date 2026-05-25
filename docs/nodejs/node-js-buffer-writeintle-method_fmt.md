# Node.js Buffer.writeIntLE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-writeintle-method/](https://www.geeksforgeeks.org/node-js-buffer-writeintle-method/)

`Buffer`是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

`Buffer.writeIntLE()`方法使用小端格式将字节长度的值写入`Buffer`对象。

## 语法

```js
Buffer.writeIntLE( value, offset, byteLength )
```

## 参数

该方法接受三个参数，如上所述，如下所述：

*   `value`：它持有要写入缓冲区的整数值。
*   `offset`：它持有整数值，即在写入缓冲区之前要跳过的字节数。`offset`的值位于 **0 <= offset <= buf.length - byteLength**。
*   `byteLength`：它持有要写入缓冲区的字节数。`byteLength`的值是 **0 < byteLength <= 6**。

## 返回值

返回一个整数值偏移量加上写入的字节数。

## 例 1

```js
// Node program to demonstrate the   
// Buffer.readInt16LE() Method

// Allocating buffer from array
var buf = Buffer.from('GeeksForGeeks');

buf.writeIntLE('ee', 0, 5);

// Printing allocated buffer
console.log(buf);

console.log(buf.toString());
```

输出：

```js
<Buffer 00 00 00 00 00 46 6f 72 47 65 65 6b 73>
     ForGeeks
```

## 例 2

```js
// Node program to demonstrate the   
// Buffer.readInt16LE() Method

// Allocating buffer from array
const buf = Buffer.allocUnsafe(4);

buf.writeIntLE(0xabcdef, 0, 4);

// Printing allocated buffer
console.log(buf);
```

输出：

```js
<Buffer ef cd ab 00>
```

## 注意

以上程序使用`node index.js`命令编译运行。

## 参考

[https://nodejs.org/api/buffer.html#buffer_buf_writeintle_value_offset_bytelength](https://nodejs.org/api/buffer.html#buffer_buf_writeintle_value_offset_bytelength)