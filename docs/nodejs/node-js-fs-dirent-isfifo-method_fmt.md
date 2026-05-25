# Node.js `fs.Dirent.isFIFO()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-dirent-isfifo-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-isfifo-method/)

`fs.Dirent.isFIFO()` 方法是 `fs` 模块（文件系统）中 `Dirent` 类的内置 API，用于检查特定目录项是否描述了一个先进先出（FIFO）管道。

## 语法

```js
const dirent.isFIFO()
```

## 参数
此方法不接受任何参数。

## 返回值
如果特定目录项描述了先进先出管道，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `fs.dirent.isFIFO()` 方法在 Node.js 中的使用。

### 示例 1
**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// dirent.isFIFO() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

// Creating and initiating FIFO's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

// Synchronously reading the FIFO's
  // underlying resource handle
  // using readSync() method
  for(var i = 0; i <= 3; i ++ ) {

// Checking if the particular dirent is
    // FIFO or not by using isFIFO() method
    const value = (dir.readSync()).isFIFO();

// Display the result
    console.log(dir.readSync());
    console.log(value);
  }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'filename.txt', [Symbol(type)]: 1 }
false
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

### 示例 2
**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// dirent.isFIFO() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

let dir = null;

try {

// Creating and initiating directory's
    // underlying resource handle
    dir = await fs.promises.opendir(
        new URL('file:///F:/java/'));

// Synchronously reading the FIFO's
    // underlying resource handle
    // using readSync() method
    for(var i = 0; i <= 3; i ++ ) {

// Checking if the particular dirent is
      // FIFO or not by using isFIFO() method
      const value = (dir.readSync()).isFIFO();

// Display the result
      console.log(dir.readSync());
      console.log(value);
    }
  } finally {

if (dir) {

// Display the result
      console.log("dir is closed successfully");

// Synchronously closeSyncing the directory's
      // underlying resource handle
      const promise = dir.closeSync();
    }
  }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'features', [Symbol(type)]: 2 }
false
Dirent { name: 'GFG.class', [Symbol(type)]: 1 }
false
dir is closed successfully
```

**参考资料:** [https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isfifo](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isfifo)