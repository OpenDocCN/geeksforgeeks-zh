# Node.js `fs.Dirent.isSocket()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-dirent-issocket-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-issocket-method/)

`fs.Dirent.isSocket()` 方法是 `fs` 模块中 `Directory` 类的内置应用编程接口，用于检查特定目录项是否描述了一个套接字。

**语法:**
```js
const dirent.isSocket()
```

**参数:** 此方法不接受任何参数。
**返回值:** 如果特定目录项描述了套接字，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `fs.dirent.isSocket()` 方法在 Node.js 中的使用。

## 示例 1

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// dirent.isSocket() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating dir's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the dir's
  // underlying resource handle
  // using readSync() method
  for(var i = 0; i <= 3; i ++ ) {

    // Checking if the particular
    // dirent is Socket or not
    // by using isSocket() method
    const value = (dir.readSync()).isSocket();

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
```
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'filename.txt', [Symbol(type)]: 1 }
false
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

## 示例 2

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// dirent.isSocket() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating dir's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the dir's
  // underlying resource handle
  // using readSync() method
  for(var i = 0; i <= 3; i ++ ) {

    // Checking if the particular
    // dirent is Socket or not
    // by using isSocket() method
    const value = (dir.readSync()).isSocket();

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
```
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

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_issocket](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_issocket)