# Node.js Buffer.writeUIntLE()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-writeuintle-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuintle-method/)

`Buffer.writeUIntLE()`方法用于使用小端字节向Buffer对象写入指定的字节。它支持高达48位的精度。当使用非无符号整数的值时，其行为是未定义的。

## 语法

```js
Buffer.writeUIntLE( value, offset, byteLength )
```

## 参数

该方法接受三个参数，如下所述：

*   `value`：指定要写入Buffer对象的数字。
*   `offset`：指定在写入缓冲区之前要跳过的字节数。`offset`的值在`0 <= offset <= buf.length - byteLength`范围内。
*   `byteLength`：指定写入缓冲区的字节数。`byteLength`的值在`0 < byteLength <= 6`范围内。

## 返回值

返回偏移量加上写入的字节数。

## 示例

下面的例子说明了在Node.js中使用`Buffer.writeUIntLE()`方法：

### 示例 1

```js
// Node.js program to demonstrate the
// Buffer.writeUIntLE() method

// Creating a buffer of size 4
const buffer_1 = Buffer.allocUnsafe(4);

// Writes byteLength bytes of value to buf
// at the specified offset.
buffer_1.writeUIntLE(0x12127474, 0, 4);

// Display the result
console.log(buffer_1);

// Creating a buffer of size 6
const buffer_2 = Buffer.allocUnsafe(6);
buffer_2.writeUIntLE(0x12127474abcd, 0, 6);

// Display the result
console.log(buffer_2);
```

**输出：**

```js
<Buffer 74 74 12 12>
<Buffer cd ab 74 74 12 12>
```

### 示例 2

```js
// Node.js program to demonstrate the
// Buffer.writeUIntLE() method

// Creating a buffer of given size
const buffer = Buffer.allocUnsafe(8);
//Before writing anything
console.log("Before filling buffer");
console.log(buffer);

// to fill first 6 bytes, take offset 0
// and bytelength 6
console.log("After filling 6 bytes");
buffer.writeUIntLE(0xcc1267280012, 0, 6);
console.log(buffer);

// to fill next 2 bytes add 6 offet
// and bytelength 2
console.log("After filling next 2 bytes");
buffer.writeUIntLE(0x1112, 6, 2)
console.log(buffer);
```

**输出：**

```js
Before filling buffer
<Buffer 00 00 00 00 00 00 00 00>
After filling 6 bytes
<Buffer 12 00 28 67 12 cc 00 00>
After filling next 2 bytes
<Buffer 12 00 28 67 12 cc 12 11>
```

## 注意事项

以上程序使用`node index.js`命令编译运行。

## 参考

[https://nodejs.org/api/buffer.html#buffer_buf_writeuintle_value_offset_bytelength](https://nodejs.org/api/buffer.html#buffer_buf_writeuintle_value_offset_bytelength)