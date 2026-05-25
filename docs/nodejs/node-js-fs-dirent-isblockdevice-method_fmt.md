# Node.js `fs.Dirent.isBlockDevice()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-dirent-isblockdevice-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-isblockdevice-method/)

`fs.Dirent.isBlockDevice()` 方法是 `fs` 模块中 `Dirent` 类的一个内置 API，用于检查特定目录项是否描述了一个块设备。

**语法:**

```js
const dirent.isBlockDevice()
```

**参数:** 此方法不接受任何参数。
**返回值:** 如果特定目录项描述了一个块设备，则该方法返回 `true`，否则返回 `false`。

下面的程序说明了 `fs.Dirent.isBlockDevice()` 方法在 Node.js 中的使用。

**示例 1:**

**文件名:** `index.js`

```js
// Node program to demonstrate the
// dirent.isBlockDevice() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the directory's
  // underlying resource handle using
  // readSync() method
  for(var i =0 ; i <=3 ; i ++ ){

    // Checking if the particular dirent
    // is blocked device or not by using
    // isBlockDevice() method
    const value = (dir.readSync()).isBlockDevice();

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
false
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

**示例 2:**

**文件名:** `index.js`

```js
// Node program to demonstrate the
// dirent.isBlockDevice() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises
      .opendir(new URL('file:///F:/'));

  // Synchronously reading the directory's
  // underlying resource handle using
  // readSync() method
  for (var i = 0; i <= 3; i++) {

    // Checking if the particular
    // dirent is blocked device or not
    // by using isBlockDevice() method
    const value = (dir.readSync())
                    .isBlockDevice();

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
Dirent { name: 'adonis_auth_api', [Symbol(type)]: 2 }
false
Dirent { name: 'Android Template', [Symbol(type)]: 2 }
false
Dirent { name: 'Calander', [Symbol(type)]: 2 }
false
Dirent { name: 'first-app', [Symbol(type)]: 2 }
false
```

**注意:** 以上程序不会在在线 JavaScript 和脚本编辑器上运行。

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isblockdevice](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dirent_isblockdevice)