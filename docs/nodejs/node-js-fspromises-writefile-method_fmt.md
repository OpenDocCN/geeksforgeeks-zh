# Node.js `fsPromises.writeFile()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fspromises-writefile-method/](https://www.geeksforgeeks.org/node-js-fspromises-writefile-method/)

`fsPromises.writeFile()` 方法用于将指定的数据异步写入文件。默认情况下，如果文件存在，它将被替换。“选项”参数可用于修改方法的功能。

成功之后，承诺将会毫无争议地实现。

## 语法

```js
fsPromises.writeFile( file, data, options )
```

## 参数

该方法接受三个参数，如上所述，如下所述:

*   `file`: 它是一个字符串、Buffer、URL 或文件描述符整数，指示必须写入的文件路径。使用文件描述符将使其行为类似于 `fsPromises.write()` 方法。
*   `data`: 是要写入文件的字符串、Buffer、TypedArray 或 DataView。
*   `options`: 是一个字符串或对象，可用于指定影响输出的可选参数。它有三个可选参数:
    *   `encoding`: 是一个字符串值，指定文件编码。默认值是 `utf8`。
    *   `mode`: 是一个整数值，指定文件模式。默认值是 `0o666`。
    *   `flag`: 是一个字符串值，指定写入文件时使用的标志。默认值是 `"w"`。

## 返回值

该方法返回一个承诺。

下面的例子说明了 Node.js 中的方法:

## 示例

### 例 1

```js
// Node.js program to demonstrate the 
// fsPromises.writeFile() method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;
let data = "This is a file containing"
        + " a collection of movies.";

(async function main() {
    try {
        await fsPromises.writeFile(
                "movies.txt", data)

        console.log("File written successfully");
        console.log("The written file has"
            + " the following contents:");

        console.log("" + 
            fs.readFileSync("./movies.txt"));

    } catch (err) {
        console.error(err);
    }
})();
```

**输出:**

```js
File written successfully
The written file has the following contents:     
This is a file containing a collection of movies.
```

### 例 2

```js
// Node.js program to demonstrate the 
// fsPromises.writeFile() method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;
let data = "This is a file containing"
        + " a collection of books.";

(async function main() {
    try {

        await fsPromises.writeFile(
                "books.txt", data, {
            encoding: "utf8",
            flag: "w",
            mode: 0o666
        });

        console.log("File written successfully\n");
        console.log("The written has the "
                + "following contents:");

        console.log("" + 
            fs.readFileSync("books.txt"));
    }
    catch (err) {
        console.error(err);
    }
})();
```

**输出:**

```js
File written successfully

The written has the following contents:
This is a file containing a collection of books.
```

## 参考

[https://nodejs.org/api/fs.html#fs_fspromises_writefile_file_data_options](https://nodejs.org/api/fs.html#fs_fspromises_writefile_file_data_options)