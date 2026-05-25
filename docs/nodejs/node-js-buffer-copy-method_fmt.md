# Node.js Buffer.copy()方法

> 原文：[https://www.geeksforgeeks.org/node-js-buffer-copy-method/](https://www.geeksforgeeks.org/node-js-buffer-copy-method/)

`Buffer`是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

`Buffer.copy()`方法只需将所有值从输入缓冲区复制到另一个缓冲区。

## 语法

```js
buffer.copy( target, targetStart, sourceStart, sourceEnd )
```

## 参数

这个方法接受四个参数：

*   `target`：目标缓冲区，所有值需要被复制到其中。
*   `targetStart`：目标缓冲区中开始写入元素的起始索引。其默认值为 0。
*   `sourceStart`：输入缓冲区中开始复制值的索引。其默认值为 0。
*   `sourceEnd`：输入缓冲区中完成值复制的索引。其默认值为 `buffer.length`。

## 返回值

该方法返回一个数字，指示复制的字节数。

## 注意

从输入缓冲区复制值，并将其覆盖到输出缓冲区，即使目标内存区域（索引）已经存在数据。即使目标内存区域与输入缓冲区重叠，也将数据从输入缓冲区的一个区域复制到目标缓冲区的一个区域。

下面的例子说明了 `Buffer.copy()`方法在 Node.js 中的使用：

## 例 1

```js
// Node.js program to demonstrate the
// Buffer.copy() Method

// Creating a buffer
var buffer2 = Buffer.from('for');

var buffer1 = Buffer.from('GeeksandGeeks');

buffer2.copy(buffer1, 5, 0);

console.log(buffer1.toString());
```

**输出：**

```js
GeeksforGeeks
```

## 例 2

```js
// Node.js program to demonstrate the
// Buffer.copy() Method

var buffer2 = Buffer.allocUnsafe(5);

var buffer1 = Buffer.from('Geeks');

for (let i = 0; i < 5; i++) {

    // Adds: 'a b c d e' as 97 98 99 100 101
    // are their respective ASCII values
    buffer2[i] = i + 97;
}

buffer2.copy(buffer1, 2);

// Prints 'Geabc' as the input buffer1
// carries 'Geeks' and we provided the
// targetStart index as 2
// so elements will replace the values in
// buffer1 starting from index 2

console.log(buffer1.toString());
```

**输出：**

```js
Geabc
```

**注意：** 以上程序使用 `node index.js` 命令编译运行。

**参考：** [https://nodejs.org/api/buffer.html#buffer_buf_copy_targetstart_sourcestart_sourceend](https://nodejs.org/api/buffer.html#buffer_buf_copy_targetstart_sourcestart_sourceend)