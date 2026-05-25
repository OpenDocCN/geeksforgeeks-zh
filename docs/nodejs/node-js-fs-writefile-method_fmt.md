# Node.js `fs.writeFile()`方法

> 原文：[`https://www.geeksforgeeks.org/node-js-fs-writefile-method/`](https://www.geeksforgeeks.org/node-js-fs-writefile-method/)

`fs.writeFile()`方法用于将指定的数据异步写入文件。默认情况下，如果文件存在，它将被替换。“选项”参数可用于修改方法的功能。

## 语法

```js
fs.writeFile( file, data, options, callback )
```

## 参数

这个方法接受上面提到的和下面描述的四个参数：

*   **`file`**：它是一个字符串、Buffer、URL或文件描述符整数，指示必须写入的文件的路径。使用文件描述符将使其行为类似于`fs.write()`方法。
*   **`data`**：是要写入文件的字符串、Buffer、TypedArray或DataView。
*   **`option`**：是一个字符串或对象，可用于指定影响输出的可选参数。它有三个可选参数：
    *   **`encoding`**：是一个字符串值，指定文件编码。默认值是`utf8`。
    *   **`mode`**：是一个整数值，指定文件模式。默认值是`0o666`。
    *   **`flag`**：是一个字符串值，指定写入文件时使用的标志。默认值是`"w"`。
*   **`callback`**：是一个函数，将在方法执行时被调用。
    *   **`err`**：如果操作失败将抛出的错误。

下面的例子说明了Node.js中的`fs.writeFile()`方法：

## 例1

```js
// Node.js program to demonstrate the
// fs.writeFile() method

// Import the filesystem module
const fs = require('fs');

let data = "This is a file containing a collection of books.";

fs.writeFile("books.txt", data, (err) => {
  if (err)
    console.log(err);
  else {
    console.log("File written successfully\n");
    console.log("The written has the following contents:");
    console.log(fs.readFileSync("books.txt", "utf8"));
  }
});
```

### 输出

```js
File written successfully

The written has the following contents:
This is a file containing a collection of books.
```

## 例2

```js
// Node.js program to demonstrate the
// fs.writeFile() method

// Import the filesystem module
const fs = require('fs');

let data = "This is a file containing a collection of movies.";

fs.writeFile("movies.txt", data,
  {
    encoding: "utf8",
    flag: "w",
    mode: 0o666
  },
  (err) => {
    if (err)
      console.log(err);
    else {
      console.log("File written successfully\n");
      console.log("The written has the following contents:");
      console.log(fs.readFileSync("movies.txt", "utf8"));
    }
});
```

### 输出

```js
File written successfully

The written has the following contents:
This is a file containing a collection of movies.
```

## 参考

[`https://nodejs.org/api/fs.html#fs_fs_writefile_file_data_options_callback`](https://nodejs.org/api/fs.html#fs_fs_writefile_file_data_options_callback)