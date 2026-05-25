# Node.js Buffer.writeIntBE()方法

> 原文：`https://www.geeksforgeeks.org/node-js-buffer-writeintbe-method/`

`Buffer.writeIntBE()`方法用于以大端格式在给定偏移量处将指定字节的值写入缓冲区。它支持高达 48 位的精度。如果该值是其他有符号整数，则它的行为是未定义的。

## 语法

```js
buffer.writeIntBE( value, offset, byteLength )
```

## 参数

该方法接受三个参数，如下所述：

*   `Value`：指定要写入`Buffer`对象的数字。
*   `Offset`：指定在写入缓冲区之前要跳过的字节数。`offset`的值位于 `0 <= offset <= buf.length - byteLength`。
*   `Byte Length`：指定写入缓冲区的字节数。`byteLength`的值是 `0 < byteLength <= 6`。

## 返回值

返回一个指定偏移量加上写入字节数的整数值。

## 例 1

```js
// Node.js program to demonstrate the
// Buffer.writeIntBE() method

// Creating a buffer of given size
const buffer = Buffer.allocUnsafe(6);

// Write into the buffer
buffer.writeIntBE(0x10, 0, 6);

// Display the Buffer element
console.log(buffer);

// Creating a buffer of given size
const buffer2 = Buffer.allocUnsafe(6);

// Write into the buffer
buffer2.writeIntBE(0x20, 0, 4);

// Display the Buffer element
console.log(buffer2);
```

输出：

```js
<Buffer 00 00 00 00 00 10>
<Buffer 00 00 00 20 69 74>
```

## 例 2

```js
// Node.js program to demonstrate the
// Buffer.writeIntBE() method

// Creating a buffer of given size
const buffer = Buffer.allocUnsafe(6);

// Write into the buffer
buffer.writeIntBE(023, 0, 6);

// Display the Buffer element
console.log(buffer);

// Creating a buffer of given size
const buffer2 = Buffer.allocUnsafe(6);

// Write into the buffer
buffer2.writeIntBE(1010, 0, 6);

// Display the Buffer element
console.log(buffer2);
```

输出：

```js
<Buffer 00 00 00 00 00 13>
<Buffer 00 00 00 00 03 f2>
```

## 注意

以上程序使用`node index.js`命令编译运行。

## 参考

`https://nodejs.org/api/buffer.html#buffer_buf_writeintbe_value_offset_bytelength`