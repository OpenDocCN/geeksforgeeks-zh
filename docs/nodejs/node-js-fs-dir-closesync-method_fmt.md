# Node.js `fs.Dir.closeSync()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-dir-closesync-method/](https://www.geeksforgeeks.org/node-js-fs-dir-closesync-method/)

`fs.Dir.closeSync()` 方法是 `fs` 模块（文件系统模块）中 `Dir` 类的一个内置应用编程接口，用于同步关闭目录的底层资源句柄。

## 语法

```js
const dir.closeSync()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个 `undefined` 对象。

下面的程序说明了 `fs.Dir.closeSync()` 方法的使用。

## 示例 1

**文件名:** `index.js`

### JavaScript

```js
// Node.js program to demonstrate the
// dir.closeSync() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  console.log("All the dirent before operation :- ");
  for (var i = 0; i <= 6; i++) {
    console.log(((dir.readSync())).name);
  }

  // Synchronously closeSyncing the directory's
  // underlying resource handle
  const promise = dir.closeSync();

  // Display the result
  console.log("dir is closed successfully");
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
All the dirent before operation :-
abcd.cer
books.txt
cert.cer
certfile.cer
certificate1.cer
example.txt
features
dir is closed successfully
```

## 示例 2

**文件名:** `index.js`

### JavaScript

```js
// Node.js program to demonstrate the
// dir.closeSync() method
const fs = require('fs');
const fsPromises = fs.promises;

// Name of the directory to be created
let directo = './temp';

// Checking if the directory is present or not
if (!fs.existsSync(directo)){
  fs.mkdirSync(directo);
}

// Initiating asynchronous function
async function funct(path) {

  // Initializing dir
  let dir = null;
  let pathval = null;

  try {

    // Creating and initiating directory's
    // underlying resource handle
    dir = await fs.promises.opendir(
      new URL('file:///F:/java/temp'));

    console.log("All the dirent before operation :- "
                + ((dir.readSync())));

    // Getting the path of the directory
    // by using path() method
    pathval = dir.path;

  } finally {

    if (dir) {

      // Close the file if it is opened.
      console.log("Path :- " + pathval);

      console.log("All the dirent before operation :- "
                  + ((dir.readSync())));

      console.log("dir is closed successfully");

      await dir.closeSync();  
    }
  }
}

funct('./').catch(console.error);
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
All the dirent before operation :- [object Object]
Path :- F:
All the dirent before operation :- [object Object]
dir is closed successfully
```

## 参考

[https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dir_closesync](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dir_closesync)