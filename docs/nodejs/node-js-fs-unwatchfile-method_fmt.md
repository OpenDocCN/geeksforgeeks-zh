# Node.js `fs.unwatchFile()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fs-unwatchfile-method/](https://www.geeksforgeeks.org/node-js-fs-unwatchfile-method/)

`fs.unwatchFile()` 方法用于停止监视给定文件的更改。可以指定可选的 `listener` 参数，以便仅从文件中移除指定的侦听器。否则，与该文件关联的所有侦听器都将被删除。如果在使用该函数时文件没有被监视，那么它不会执行任何操作并抛出任何错误。

## 语法

```js
fs.unwatchFile(filename[, listener])
```

## 参数

该方法接受两个参数，如下所述：

*   **`filename`**: 一个字符串、Buffer 或网址，表示需要停止监视的文件。
*   **`listener`**: 一个函数，指定之前使用 `fs.watchFile()` 函数附加的侦听器。如果指定了此参数，则仅移除该特定侦听器。这是一个可选参数。

下面的例子说明了 Node.js 中的 `fs.unwatchFile()` 方法。

## 例 1

```js
// Node.js program to demonstrate the 
// fs.unwatchFile() method

// Import the filesystem module
const fs = require('fs');

// Start watching the file
fs.watchFile("example_file.txt", (curr, prev) => {
  console.log("\nThe file was edited");
  console.log("Previous Modified Time:", prev.mtime);
  console.log("Current Modified Time:", curr.mtime);
});

// Make Changes to the file before 
// it has been stopped watching
setTimeout(
  () => fs.writeFileSync("example_file.txt",
         "File Contents are Edited"),
  3000
);

// Stop watching the file
setTimeout(() => {
  fs.unwatchFile("example_file.txt");
  console.log("\n> File has been stopped watching");
}, 6000);

// Make Changes to the file after
// it has been stopped watching
setTimeout(
  () => fs.writeFileSync("example_file.txt",
         "File Contents are Edited Again"),
  9000
);
```

**输出:**

```js
The file was edited
Previous Modified Time: 2020-05-30T08:43:28.216Z
Current Modified Time: 2020-05-30T08:43:37.208Z

File has been stopped watching
```

## 例 2

```js
// Node.js program to demonstrate 
// the fs.unwatchFile() method

// Import the filesystem module
const fs = require('fs');

// Defining 2 listeners for watching the file
let listener1 = (curr, prev) => {
  console.log("Listener 1: File Modified");
};
let listener2 = (curr, prev) => {
  console.log("Listener 2: File Modified");
};

// Using both the listeners on one file
fs.watchFile("example_file.txt", listener1);
fs.watchFile("example_file.txt", listener2);

// Modify the file contents
setTimeout(
  () => fs.writeFileSync("example_file.txt",
         "File Contents are Edited"),
  3000
);

// Stop using the first listener
setTimeout(() => {
  fs.unwatchFile("example_file.txt", listener1);
  console.log("\n> Listener 1 has been stopped!\n");
}, 6000);

// Modify the file contents again
setTimeout(
  () => fs.writeFileSync("example_file.txt",
         "File Contents are Edited Again"),
  9000
);
```

**输出:**

```js
Listener 1: File Modified
Listener 2: File Modified

Listener 1 has been stopped!

Listener 2: File Modified
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_unwatchfile_filename_listener](https://nodejs.org/api/fs.html#fs_fs_unwatchfile_filename_listener)