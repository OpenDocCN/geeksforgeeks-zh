# Node.js `fs.appendFile()` 函数

> 原文: [https://www.geeksforgeeks.org/node-js-fs-appendfile-function/](https://www.geeksforgeeks.org/node-js-fs-appendfile-function/)

`fs.appendFile()` 方法用于将给定数据异步追加到文件中。如果新文件不存在，则会创建一个新文件。`options` 参数可用于修改操作的行为。

## 语法

```js
fs.appendFile( path, data[, options], callback )
```

## 参数

该方法接受上面提到的四个参数，如下所述：

*   **Path**: 一个字符串、Buffer、网址或数字，表示要追加内容的源文件名称或文件描述符。
*   **Data**: 一个字符串或 Buffer，表示必须追加的数据。
*   **Option**: 一个字符串或对象，可用于指定影响输出的可选参数。有三个可选参数：
    *   **encoding**: 一个字符串，指定文件编码。默认值是 `utf8`。
    *   **mode**: 一个整数，指定文件模式。默认值是 `0o666`。
    *   **flag**: 一个字符串，指定追加到文件时要使用的标志。默认值是 `"a"`。
*   **Callback**: 一个函数，当方法执行时将被调用。
    *   **err**: 如果方法失败，将抛出此错误。

下面的例子说明了 Node.js 中的 `fs.appendFile()` 方法：

## 示例 1

该示例显示了给定文本到文件的追加。

```js
// Node.js program to demonstrate the
// fs.appendFile() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

fs.appendFile("example_file.txt", "World", (err) => {
  if (err) {
    console.log(err);
  }
  else {
    // Get the file contents after the append operation
    console.log("\nFile Contents of file after append:",
      fs.readFileSync("example_file.txt", "utf8"));
  }
});
```

**输出:**

```js
File Contents of file before append: Hello

File Contents of file after append: HelloWorld
```

## 示例 2

该示例显示了可选参数的用法，用于更改操作的文件编码、模式和标志。

```js
// Node.js program to demonstrate the
// fs.appendFile() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

fs.appendFile("example_file.txt", " - GeeksForGeeks",
  { encoding: "latin1", mode: 0o666, flag: "a" },
  (err) => {
    if (err) {
      console.log(err);
    }
    else {
      // Get the file contents after the append operation
      console.log("\nFile Contents of file after append:",
        fs.readFileSync("example_file.txt", "utf8"));
    }
  });
```

**输出:**

```js
File Contents of file before append: This is a test file

File Contents of file after append: This is a test file - GeeksForGeeks
```

**参考:** [https://nodejs.org/api/fs.html#fs_fs_appendfile_path_data_options_callback](https://nodejs.org/api/fs.html#fs_fs_appendfile_path_data_options_callback)