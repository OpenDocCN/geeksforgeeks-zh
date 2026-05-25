# Node.js `fs.Dirent.isDirectory()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-dirent-isdirectory-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-isdirectory-method/)

`fs.Dirent.isDirectory()` 方法是 `fs` 模块中 `Dirent` 类的一个内置 API，用于检查特定目录项是否描述了一个目录。

## 语法

```js
const dirent.isDirectory()
```

## 参数

此方法不接受任何参数。

## 返回值

如果特定目录项描述了目录，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了在 Node.js 中 `fs.Dirent.isDirectory()` 方法的使用:

### 示例 1

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// dirent.isDirectory() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the directory's
  // underlying resource handle using
  // readSync() method
  for(var i = 0 ; i <= 3 ; i ++ ) {

    // Checking if the particular dirent
    // is Directory or not by using
    // isDirectory() method
    const value = (dir.readSync()).isDirectory();

    // Display the result
    console.log(dir.readSync());
    console.log(value);
  }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```js
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'filename.txt', [Symbol(type)]: 1 }
true
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

### 示例 2

**文件名:** `index.js`

```js
// node.js program to demonstrate the
// dirent.isDirectory() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

  let dir = null;

  try {

    // Creating and initiating directory's
    // underlying resource handle
    dir = await fs.promises.opendir(
          new URL('file:///F:/java/'));

    // Using readSync() method
    for(var i = 0 ; i <= 3 ; i ++ ) {

      // Checking if the particular dirent
      // is Directory or not by using
      // isDirectory() method
      const value = (dir.readSync()).isDirectory();

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

```bash
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

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isdirectory](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isdirectory)