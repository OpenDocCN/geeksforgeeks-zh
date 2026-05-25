# Node.js中的缓冲区是什么？

> 原文：[https://www.geeksforgeeks.org/what-is-buffer-in-node-js/](https://www.geeksforgeeks.org/what-is-buffer-in-node-js/)

纯 JavaScript 非常适合 Unicode 编码的字符串，但是它不能很好地处理二进制数据。当我们在浏览器级别对数据执行操作时没有问题，但是在处理 TCP 流和对文件系统执行读写操作时，需要处理纯二进制数据。为了满足这一需求，Node.js 使用了 buffer，因此在本文中，我们将了解 Node.js 中的 Buffer。

## Node.js 中的 Buffers

Node.js 中的 `Buffer` 类用于对原始二进制数据执行操作。通常，缓冲区是指内存中的特定存储位置。缓冲区和数组有一些相似之处，但不同的是数组可以是任何类型，并且可以调整大小。缓冲区只处理二进制数据，不能调整大小。缓冲区中的每个整数代表一个字节。`console.log()` 函数用于打印缓冲区实例。

## 对 Buffer 执行操作的方法

| **编号** | **方法** | **描述** |
| :--- | :--- | :--- |
| one | `Buffer.alloc(size)` | 它创建一个缓冲区并为其分配大小。 |
| Two | `Buffer.from(initialization)` | 它用给定的数据初始化缓冲区。 |
| three | `Buffer.write(data)` | 它将数据写入缓冲区。 |
| four | `toString()` | 它从缓冲区读取数据并返回。 |
| five | `Buffer.isBuffer(object)` | 它检查对象是否是缓冲区。 |
| six | `Buffer.length` | 它返回缓冲区的长度。 |
| seven | `Buffer.copy(buffer, segmentSize)` | 它将数据从一个缓冲区复制到另一个缓冲区。 |
| eight | `Buffer.slice(start, end=buffer.length)` | 它返回存储在缓冲区中的数据段。 |
| nine | `Buffer.concat([buffer, buffer])` | 它连接两个缓冲区。 |

## 档案名称：`index.js`

```js
// Different Method to create Buffer
var buffer1 = Buffer.alloc(100);
var buffer2 = new Buffer('GFG');
var buffer3 = Buffer.from([1, 2, 3, 4]);

// Writing data to Buffer
buffer1.write("Happy Learning");

// Reading data from Buffer
var a = buffer1.toString('utf-8');
console.log(a);

// Check object is buffer or not
console.log(Buffer.isBuffer(buffer1));

// Check length of Buffer
console.log(buffer1.length);

// Copy buffer
var bufferSrc = new Buffer('ABC');
var bufferDest = Buffer.alloc(3);
bufferSrc.copy(bufferDest);

var Data = bufferDest.toString('utf-8');
console.log(Data);

// Slicing data
var bufferOld = new Buffer('GeeksForGeeks');
var bufferNew = bufferOld.slice(0, 4);
console.log(bufferNew.toString());

// concatenate two buffer
var bufferOne = new Buffer('Happy Learning ');
var bufferTwo = new Buffer('With GFG');
var bufferThree = Buffer.concat([bufferOne, bufferTwo]);
console.log(bufferThree.toString());
```