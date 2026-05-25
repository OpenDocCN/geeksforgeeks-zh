# Node.js filehandle.read()方法

> 原文: [https://www.geeksforgeeks.org/node-js-filehandle-read-method/](https://www.geeksforgeeks.org/node-js-filehandle-read-method/)

`filehandle.read()` 方法使用文件描述符读取文件。为了读取没有文件描述符的文件，可以使用 `filehandle` 包的 `readFile()` 方法。

Node.js 用于服务器端脚本。读取和写入文件是任何应用程序中执行的两个最重要的操作。Node.js 提供了广泛的内置功能来执行读写操作。`fs` 包包含文件操作所需的功能。

## 语法

```js
filehandle.read( buffer, offset, length, position );
```

## 参数

该函数接受上面提到的和下面描述的四个参数：

*   `buffer`: 存储从文件获取的数据。它是数据将被写入的缓冲区。
*   `offset`: 缓冲区中的偏移量，指示写入开始的位置。
*   `length`: 一个整数，指定要读取的字节数。
*   `position`: 一个整数，指定在文件中从哪里开始读取。`position` 是一个参数，指定在文件中从哪里开始读取。如果该位置为空，则从当前文件位置读取数据。

## 返回值

返回一个 `Promise`。

## 注意

`GFG.txt` 应出现在目录中，文本如下：

```js
GeeksforGeeks - A computer science portal for geeks
```

## 例

```js
// Node.js program to demonstrate the
// Node.js filehandle.read() Method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = fs.promises;

var buffer = new Buffer.alloc(1024);

console.log(fs.readFileSync('GFG.txt', 'utf8'));

// Using the async function to 
// ReadFile using filehandle
async function doRead() {
    let filehandle = null;

    try {
        // Using the filehandle method
        filehandle = await fsPromises
                    .open('GFG.txt', 'r+');

        // Calling the filehandle.read() method
        await filehandle.read(buffer,
                0, buffer.length, 0);
    } finally {
        if (filehandle) {
            // Close the file if it is opened.
            await filehandle.close();
        }
    }
}

doRead().catch(console.error);
```

使用以下命令运行 `app.js` 文件：

```js
node app.js
```

## 输出

```js
GeeksforGeeks - A computer science portal for geeks
```