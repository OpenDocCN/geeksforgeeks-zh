# Node.js `filehandle.readFile()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-filehandle-readfile-method/](https://www.geeksforgeeks.org/node-js-filehandle-readfile-method/)

`filehandle.readFile()`方法用于异步读取文件内容。此方法将整个文件读入缓冲区。它异步读取文件的全部内容。

## 语法

```js
filehandle.readFile( options )
```

## 参数

该方法如上所述接受单个参数，如下所述:

*   `options`: 保存文件的编码。其默认值为 `"utf8"`。它是一个对象或字符串。
    *   `code`: 是一个字符串或空。默认：空

## 返回值

返回一个 `Promise`。

*   `Promise` 将通过文件内容解决。如果未在 `options.encoding` 中指定编码，数据将作为 `Buffer` 对象返回。否则，数据将是一个字符串。
*   如果 `options` 是一个字符串，则指定编码。
*   **文件句柄**必须支持读取。

## 示例

读取文件 `gfg.txt` 的文件内容。

**注意:** `gfg.txt` 应出现在目录中，并带有以下文本:

```js
GeeksforGeeks - A computer science portal for geeks
```

**文件名: app.js**

```js
// Node.js program to demonstrate the   
// fsPromises.truncate() Method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = fs.promises;

// Using the async function to
// ReadFile using filehandle
async function doReadFile() {
    let filehandle = null;
    try {

// Using the filehandle method
        filehandle = 
        await fsPromises.open('GFG.txt', 'r+');

var data = 
        await filehandle.readFile("utf8");

console.log(data);
    } catch (e) {
        console.log("Error", e);
    }
}

doReadFile().catch((error) => {
    console.log("Error", error)
});
```

使用以下命令运行 `app.js` 文件:

```js
node app.js
```

## 输出

```js
GeeksforGeeks - A computer science portal for geeks
```

## 参考

[https://nodejs.org/dist/latest-v14.x/docs/api/fs.html#fs_filehandle_readfile_options](https://nodejs.org/dist/latest-v14.x/docs/api/fs.html#fs_filehandle_readfile_options)