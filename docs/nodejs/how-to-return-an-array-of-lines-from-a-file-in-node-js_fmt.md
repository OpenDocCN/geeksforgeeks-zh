# 如何从 node.js 中的一个文件返回一个行数组？

> 原文: [https://www.geeksforgeeks.org/how-to-return-an-array-of-lines-from-a-file-in-node-js/](https://www.geeksforgeeks.org/how-to-return-an-array-of-lines-from-a-file-in-node-js/)

在本文中，我们将使用 node.js 从指定的文件中返回一个行数组。`fs` 模块用于处理 node.js 中的文件系统，并读取文件数据，我们使用 `fs.readFileSync()` 或 `fs.readFile()` 方法。这里我们将使用 `readFileSync` 方法读取文件，我们使用下面的步骤以数组的形式返回文件的行:

*   使用 `fs.readFileSync` 方法来读取文件的数据，你会得到一个 buffer。
*   使用 `toString()` 方法。
*   将 buffer 转换为字符串。现在使用 `string.split()` 方法来分割数据，分隔符应该是 `"\n"`。

下面是我们实现上述步骤的示例:

## index.js

```js
// Requiring the fs module
let fs = require("fs")

// Creating a function which takes a file as input
const readFileLines = filename =>
  fs
    .readFileSync(filename)
    .toString('UTF8')
    .split('\n');

// Driver code
let arr = readFileLines('gfg.txt');

// Print the array
console.log(arr);
```

**文本文件:** `gfg.txt` 文件。

```js
Geeksforgeeks
A computer Science Portal for Geeks
```

使用以下命令运行代码:

```js
node index.js
```

**输出:**

```js
[
  'Geeksforgeeks',
  'A computer Science Portal for Geeks'
]
```