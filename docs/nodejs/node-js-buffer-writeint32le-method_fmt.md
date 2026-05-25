# Node.js Buffer.writeInt32LE()方法

> 原文：`https://www.geeksforgeeks.org/node-js-buffer-writeint32le-method/`

`Buffer.writeInt32LE()`方法用于使用小端格式将指定的字节写入缓冲区。该值包含有效的带符号 32 位整数。如果该值包含其他带符号的 32 位整数，则它的行为是未定义的。

## 语法

```js
Buffer.writeInt32LE( value, offset )
```

## 参数

该方法接受两个参数，如下所述：

*   `value`：一个整数值，表示要写入缓冲区的值。
*   `offset`：一个整数值，表示写入前要跳过的字节数，偏移量范围为 **0 到 `buffer.length–4`**。其默认值为 0。

## 返回值

返回偏移量加上写入的字节数。

## 示例

### 例 1

```js
// Node.js program to demonstrate the
// Buffer.writeInt32LE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(8);

// Write the buffer element in LE format
buf.writeInt32LE(0x05060708, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in LE format
buf.writeInt32LE(0x05060708, 4);

// Display the buffer list
console.log(buf);
```

**输出：**

```js
<Buffer 08 07 06 05 00 00 00 00>
<Buffer 08 07 06 05 08 07 06 05>
```

### 例 2

```js
// Node.js program to demonstrate the
// Buffer.writeInt32LE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(8);

// Write the buffer element in LE format
buf.writeInt32LE(0x12345678, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in LE format
buf.writeInt32LE(0x123456, 4);

// Display the buffer list
console.log(buf);
```

**输出：**

```js
<Buffer 78 56 34 12 63 65 73 73>
<Buffer 78 56 34 12 56 34 12 00>
```

**注意：** 以上程序使用 `node index.js` 命令编译运行。

**参考：** `https://nodejs.org/api/buffer.html#buffer_writeint32le_value_offset`