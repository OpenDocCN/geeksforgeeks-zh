# Node.js `fs.Dir.readSync()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-dir-readsync-method/](https://www.geeksforgeeks.org/node-js-fs-dir-readsync-method/)

`fs.Dir.readSync()` 方法是 `fs` 模块（文件系统模块）中 `Dir` 类的一个内置 API，用于同步读取目录的下一个目录条目。

## 语法

```js
const dir.readSync()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回一个 `fs.Dirent` 对象或 `null`。

以下程序说明了在 Node.js 中 `fs.Dir.readSync()` 方法的使用：

## 示例 1

**文件名：** `index.js`

```js
// Node.js program to demonstrate the
// dir.readSync() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the directory's
  // underlying resource handle
  const dirent = dir.readSync();

  // Display the result
  console.log(dirent.name);
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
abcd.cer
```

## 示例 2

**文件名：** `index.js`

```js
// Node.js program to demonstrate the
// dir.readSync() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  let dir = null;

  try {

    // Creating and initiating directory's
    // underlying resource handle
    dir = await fs.promises.opendir(
        new URL('file:///F:/java/'));

    // Synchronously reading the directory's
    // underlying resource handle
    // using readSync() method
    for(var i = 0 ; i <= 3 ; i ++ ) {
      var dirent = dir.readSync();

      // Display the result
      console.log(dirent.name);
    }

  } finally {

    if (dir) {

      // Display the result
      console.log("dir is closed successfully");

      // Synchronously closing the
      // directory's underlying resource
      // handle
      const promise = dir.closeSync()
    }
  }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
abcd.cer
cert.cer
certfile.cer
certificate1.cer
dir is closed successfully
```

## 参考
[https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dir_readsync](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dir_readsync)