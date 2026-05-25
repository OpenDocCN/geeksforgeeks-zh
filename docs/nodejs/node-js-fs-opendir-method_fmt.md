# Node.js `fs.opendir()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-fs-opendir-method/](https://www.geeksforgeeks.org/node-js-fs-opendir-method/)

`fs.opendir()`方法用于异步打开文件系统中的一个目录。它会创建一个`fs.Dir`对象来表示目录。该对象包含可用于访问目录的各种方法。

## 语法

```js
fs.opendir( path[, options], callback )
```

## 参数

该方法接受三个参数，如下所述：

*   **`path`**：一个字符串、Buffer或URL，表示必须打开的目录的路径。
*   **`options`**：一个字符串或对象，可用于指定将影响输出的可选参数。它有两个可选参数：
    *   **`encoding`**：一个字符串，指定打开目录时路径的编码以及后续读取操作的编码。默认值为`'utf8'`。
    *   **`bufferSize`**：一个数字，指定读取目录时在内部缓冲的目录条目数量。更高的值意味着更高的性能，但也会导致更高的内存使用量。默认值为`32`。
*   **`callback`**：一个函数，将在方法执行时被调用。
    *   **`err`**：如果方法失败，将抛出此错误。
    *   **`dir`**：一个由该方法创建的`fs.Dir`对象，表示该目录。

## 示例

下面的例子说明了Node.js中的`fs.opendir()`方法：

### 例 1

```js
// Node.js program to demonstrate the
// fs.opendir() method

// Import the filesystem module
const fs = require('fs');

// Open the directory
console.log("Opening the directory");
fs.opendir(

// Path of the directory
  "example_dir",

// Options for modifying the operation
  { encoding: "utf8", bufferSize: 64 },

// Callback with the error and returned
  // directory
  (err, dir) => {
    if (err) console.log("Error:", err);
    else {
      // Print the pathname of the directory
      console.log("Path of the directory:", dir.path);

      // Close the directory
      console.log("Closing the directory");
      dir.closeSync();
    }
  }
);
```

**输出：**

```js
Opening the directory
Path of the directory: example_dir
Closing the directory
```

### 例 2

```js
// Node.js program to demonstrate the
// fs.opendir() method

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
fs.opendir("example_dir", (err, dir) => {
  if (err) console.log("Error:", err);
  else {
    // Print the pathname of the directory
    console.log("\nPath of the directory:", dir.path);

    // Read the files in the directory
    // as fs.Dirent objects
    console.log("First Dirent:", dir.readSync());
    console.log("Next Dirent:", dir.readSync());
    console.log("Next Dirent:", dir.readSync());
  }
});
```

**输出：**

```js
Current filenames in directory:
file_a.txt
file_b.txt

Path of the directory: example_dir
First Dirent: Dirent { name: 'file_a.txt', [Symbol(type)]: 1 }
Next Dirent: Dirent { name: 'file_b.txt', [Symbol(type)]: 1 }
Next Dirent: null
```

## 参考

[https://nodejs.org/api/fs.html#fs_fs_opendir_path_options_callback](https://nodejs.org/api/fs.html#fs_fs_opendir_path_options_callback)