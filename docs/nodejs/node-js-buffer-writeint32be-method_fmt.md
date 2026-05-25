# Node.js Buffer.writeInt32BE()方法

> 原文: [https://www.geeksforgeeks.org/node-js-buffer-writeint32be-method/](https://www.geeksforgeeks.org/node-js-buffer-writeint32be-method/)

`Buffer.writeInt32BE()`方法是`Buffer`模块内类`Buffer`的内置应用编程接口，用于以大端格式将整数值写入指定偏移量处的`Buffer`，整数值应为有效的带符号32位整数。如果该值超出有符号32位整数的范围，则会引发错误。整数值被解释并写成二进制补码有符号整数。

## 语法

```js
Buffer.writeInt32BE( value, offset )
```

## 参数

该方法接受两个参数，如下所述：
*   `value`：该参数保存需要写入缓冲区的32位有符号整数。
*   `offset`：此参数保存一个整数值，即开始写入缓冲区之前要跳过的字节数。偏移值介于`0`到`buf.length–4`之间。它是一个可选参数，默认值为`0`。

## 返回值

该方法返回一个整数值，即偏移量加上写入的字节数之和。

## 示例

下面的例子说明了Node.js中`buf.writeInt32BE()`方法的使用：

### 例 1

```js
// Node.js program to demonstrate the
// Buffer.writeInt32BE() Method

// Allocating buffer space of 4 bytes
const buf = Buffer.allocUnsafe(4);

// Writing the value to the buffer
buf.writeInt32BE(0x7bcaf892);

// Display the buffer to stdout
console.log(buf);
```

**输出:**

```js
<Buffer 7b ca f8 92>
```

### 例 2

```js
// Node.js program to demonstrate the
// Buffer.writeInt32BE() Method

// Allocating buffer space of 8 bytes
const buf = Buffer.allocUnsafe(8);

// Writing the value to the buffer from 0 offset
buf.writeInt32BE(0x7bcaf983, 0);

// Writing the value to the buffer from 4 offset
buf.writeInt32BE(0x7fffffff, 4);

// Display the buffer to stdout
console.log(buf);
```

**输出:**

```js
<Buffer 7b ca f9 83 7f ff ff ff>
```

### 例 3

此示例将显示一条错误消息，因为偏移量大于限制，即偏移量值不在`0`到`buf.length–4`范围内。

```js
// Node.js program to demonstrate the
// Buffer.writeInt32BE() Method

// Allocating buffer space of 8 bytes
const buf = Buffer.allocUnsafe(8);

// Writing the value to the buffer from 0 offset
buf.writeInt32BE(0x7bcaf983, 0);

// Writing the value to the buffer from 4 offset
buf.writeInt32BE(0x7fffffff, 5);

// Display the buffer to stdout
console.log(buf);
```

**输出:**

```js
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 5. Received 6
```

**参考:** [https://nodejs.org/api/buffer.html#buffer_buf_writeint32be_value_offset](https://nodejs.org/api/buffer.html#buffer_buf_writeint32be_value_offset)