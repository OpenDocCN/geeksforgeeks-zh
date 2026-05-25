# 来自 `fs` 的 Node.js `stats.isFile()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-stats-isfile-method-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-isfile-method-from-fs-stats-class/)

`stats.isFile()` 方法是 `fs` 内置的应用编程接口。用于检查 `fs.Stats` 对象是否描述一个文件。

## 语法

```js
stats.isFile();
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个布尔值，如果是 `true` 则表示 `fs.Stats` 对象描述一个文件，否则为 `false`。

下面的例子说明了 `stats.isFile()` 方法在 Node.js 中的使用：

## 例 1

```js
// Node.js program to demonstrate the   
// stats.isFile() method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isFile() method
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;

// console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isFile());
});

fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;

// console.log(`stats: ${JSON.stringify(stats)}`);
    if (stats.isFile()) {
        console.log("fs.Stats describes a file");
    } else {
        console.log("fs.Stats does not describe a file");
    }
});
```

### 输出

```js
true
fs.Stats describes a file
```

## 例 2

```js
// Node.js program to demonstrate the   
// stats.isFile() method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isFile() method
fs.stat('./', (err, stats) => {
    if (err) throw err;

// console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isFile());
});

fs.stat('./', (err, stats) => {
    if (err) throw err;

// console.log(`stats: ${JSON.stringify(stats)}`);
    if (stats.isFile()) {
        console.log("fs.Stats describes a file");
    } else {
        console.log("fs.Stats does not describe a file");
    }
});
```

### 输出

```js
false
fs.Stats does not describe a file
```

## 注意

以上程序使用 `node filename.js` 命令编译运行，正确使用 `file_path`。

## 参考资料

[https://nodejs.org/api/fs.html#fs_stats_isfile](https://nodejs.org/api/fs.html#fs_stats_isfile)