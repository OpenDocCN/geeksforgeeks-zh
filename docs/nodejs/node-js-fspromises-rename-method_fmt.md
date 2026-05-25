# Node.js `fsPromises.rename()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fspromises-rename-method/](https://www.geeksforgeeks.org/node-js-fspromises-rename-method/)

`fsPromises.rename()`方法用于将给定旧路径的文件异步重命名为给定新路径。如果目标文件已经存在，它将覆盖该文件。它返回一个 Promise，成功后没有参数。

## 语法

```js
fsPromises.rename( oldPath, newPath )
```

## 参数

该方法接受两个参数，如下所述：

*   `oldPath`：要重命名的文件的旧路径。它可以是一个字符串、Buffer 或 URL。
*   `newPath`：文件需要重命名后保存的新路径。它可以是一个字符串、Buffer 或 URL。

下面的例子说明了 Node.js 中的`fsPromises.rename()`方法：

### 示例 1

本示例使用`fsPromises.rename()`方法重命名文件：

```js
// Node.js program to demonstrate the     
// fsPromises.rename() method

// Import filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

// List all the filenames before renaming 
getCurrentFilenames();

(async function main() {
    try {

// Rename the file 
        fsPromises.rename('GFG.txt', 'GeeksforGeeks.txt')
        console.log("\nFile Renamed!\n");

// List all the filenames after renaming 
        getCurrentFilenames();

} catch (err) {
        console.error(err);
    }
})();

// Function to get current filenames 
// in directory 
function getCurrentFilenames() {
    console.log("Current filenames:");
    fs.readdirSync(__dirname).forEach(file => {
        console.log(file);
    });
}
```

**输出：**

```js
Current filenames:
GFG.txt
GeeksforGeeks.js

File Renamed!

Current filenames:
GeeksforGeeks.js
GFG.txt
```

### 示例 2

本示例使用`fsPromises.rename()`方法演示文件重命名过程中出现的错误：

```js
// Node.js program to demonstrate the     
// fsPromises.rename() method

// Import filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

(async function main() {
    try {

// List all the filenames before renaming 
        getCurrentFilenames();

// Rename the file 
        fsPromises.rename('GeeksforGeeks.txt', 'geeks.txt')

// List all the filenames after renaming 
        console.log("\nFile Renamed\n");

// List all the filenames after renaming 
        getCurrentFilenames();
    }
    catch (err) {
        console.error(err);
    }
})();

// Function to get current filenames 
// in directory 
function getCurrentFilenames() {
    console.log("Current filenames:");
    fs.readdirSync(__dirname).forEach(file => {
        console.log(file);
    });
}
```

**输出：**

```js
Current filenames:
index.js
package.json
world.txt
[Error: ENOENT: no such file or directory, rename  
'G:\tutorials\nodejs-fs-rename\GeeksforGeeks.txt' ->
'G:\tutorials\nodejs-fs-rename\geeks.txt'] {
 errno: -4058,
 code: 'ENOENT',
 syscall: 'rename',
 path: 'G:\\tutorials\\nodejs-fs-rename\\GeeksforGeeks.txt',
 dest: 'G:\\tutorials\\nodejs-fs-rename\\geeks.txt'
}
```

**参考：**[https://nodejs.org/api/fs.html#fs_fspromises_rename_oldpath_newpath](https://nodejs.org/api/fs.html#fs_fspromises_rename_oldpath_newpath)