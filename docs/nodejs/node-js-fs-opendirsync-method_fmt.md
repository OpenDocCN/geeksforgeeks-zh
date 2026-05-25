# Node.js `fs.opendirSync()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-opendirsync-method/](https://www.geeksforgeeks.org/node-js-fs-opendirsync-method/)

`fs.opendirSync()`方法用于同步打开文件系统中的一个目录。它返回一个`fs.Dir`对象，用于表示目录。该对象包含可用于访问目录的各种方法。

## 语法:
```js
fs.opendirSync( path[, options] )
```

## 参数:
该方法接受两个参数，如下所述:

*   `path`: 一个字符串、Buffer或URL，表示要打开的目录的路径。
*   `options`: 一个字符串或对象，可用于指定影响输出的可选参数。它有两个可选参数:
    *   `encoding`: 一个字符串，指定打开目录时路径的编码以及后续读取操作的编码。默认值为`utf8`。
    *   `bufferSize`: 一个数字，指定读取目录时在内部缓冲的目录条目数量。更高的值意味着更高的性能，但也会导致更高的内存使用量。默认值为`32`。

## 返回值:
返回一个`fs.Dir`对象，表示目录并包含可用于访问它的各种方法。

下面的例子说明了Node.js中的`fs.opendirSync()`方法:

## 例 1:
```js
// Node.js program to demonstrate the
// fs.opendirSync() method

// Import the filesystem module
const fs = require('fs');

// Open the directory
console.log("Opening the directory");
let openedDir = fs.opendirSync("example_dir");

// Print the pathname of the directory
console.log("\nPath of the directory:", openedDir.path);

// Close the directory
console.log("\nClosing the directory");
openedDir.closeSync();
```

**输出:**
```js
Opening the directory

Path of the directory: example_dir

Closing the directory
```

## 例 2:
```js
// Node.js program to demonstrate the
// fs.opendirSync() method

// Import the filesystem module
const fs = require('fs');

// Function to get current filenames
// in directory
filenames = fs.readdirSync("example_dir");

console.log("\nCurrent filenames in directory:");
filenames.forEach((file) => {
  console.log(file);
});

// Open the directory
openedDir = fs.opendirSync("example_dir");

// Print the pathname of the directory
console.log("\nPath of the directory:", openedDir.path);

// Read the files in the directory
// as fs.Dirent objects
console.log("First Dirent:", openedDir.readSync());
console.log("Next Dirent:", openedDir.readSync());
console.log("Next Dirent:", openedDir.readSync());
```

**输出:**
```js
Current filenames in directory:
example1.txt
example2.txt

Path of the directory: example_dir
First Dirent: Dirent { name: 'example1.txt', [Symbol(type)]: 1 }
Next Dirent: Dirent { name: 'example2.txt', [Symbol(type)]: 1 }
Next Dirent: null
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_opendirsync_path_options](https://nodejs.org/api/fs.html#fs_fs_opendirsync_path_options)