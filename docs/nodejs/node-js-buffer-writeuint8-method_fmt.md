# Node.js `Buffer.writeUInt8()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-writeuint8-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint8-method/)

`Buffer.writeUInt8()` 方法是 `Buffer` 模块中 `Buffer` 类的内置 API，用于将值写入指定偏移量处的缓冲区。该值应为有效的无符号 8 位整数，否则行为未定义。

## 语法

```js
Buffer.writeUInt8( value, offset )
```

## 参数

该方法接受两个参数，如下所述：

*   `value`：要写入缓冲区的无符号整数值。
*   `offset`：指示在写入缓冲区之前要跳过的字节数。`offset` 的范围为 `0 <= offset <= buf.length–1`。`offset` 的默认值为 0。

## 返回值

返回在指定偏移量插入值的缓冲区。

## 示例

下面的例子说明了 `Buffer.writeUInt8()` 方法在 Node.js 中的使用：

### 例 1

```js
// Node.js program to demonstrate the
// Buffer.writeUInt8() method

// Creating a buffer
const buf = Buffer.allocUnsafe(5);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x14, 0);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x15, 1);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x16, 4);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x17, 3);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x18, 2);

// Display the result
console.log(buf);
```

**输出：**

```js
<Buffer 14 00 00 00 d6>
<Buffer 14 15 00 00 d6>
<Buffer 14 15 00 00 16>
<Buffer 14 15 00 17 16>
<Buffer 14 15 18 17 16>
```

### 例 2

```js
// Node.js program to demonstrate the
// Buffer.writeUInt8() method

// Creating a buffer
const buf = Buffer.allocUnsafe(3);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x11, 0);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x22, 1);

// Display the buffer
console.log(buf);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x33, 2);

// Display the buffer
console.log(buf);
```

**输出：**

```js
<Buffer 11 e7 31>
<Buffer 11 22 31>
<Buffer 11 22 33>
```

## 注意

以上程序使用 `node index.js` 命令编译运行。

## 参考

[https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_writeuint8_value_offset](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_writeuint8_value_offset)