# Node.js `stats.isFIFO()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-stats-isfifo-method/](https://www.geeksforgeeks.org/node-js-stats-isfifo-method/)

`stats.isFIFO()` 方法是 `fs` 模块的内置应用编程接口。用于检查 `fs.Stats` 对象描述的文件是否是一个先进先出（FIFO）管道。

## 语法

```js
stats.isFIFO();
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个布尔值，如果 `fs.Stats` 对象描述的是一个先进先出（FIFO）管道则为 `true`，否则为 `false`。

下面的例子说明了 `stats.isFIFO()` 方法在 Node.js 中的使用：

## 例 1

```js
// Node.js program to demonstrate the
// stats.isFIFO() Method

// Accessing fs module
const fs = require('fs');

// Calling isFIFO() method from
// fs.Stats class
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isFIFO());
    if (stats.isFIFO()) {
        console.log("fs.Stats describes a "
            + "first-in-first-out (FIFO) pipe.");
    } else {
        console.log("fs.Stats does not describe a"
            + " first-in-first-out (FIFO) pipe.");
    }
});

fs.stat('./', (err, stats) => {
    if (err) throw err;

    //console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isFIFO());
    if (stats.isFIFO()) {
        console.log("fs.Stats describes a "
            + "first-in-first-out (FIFO) pipe.");
    } else {
        console.log("fs.Stats does not describe a "
            + "first-in-first-out (FIFO) pipe.");
    }
});
```

**输出:**

```js
false
fs.Stats does not describe a a first-in-first-out (FIFO) pipe.
false
fs.Stats does not describe a a first-in-first-out (FIFO) pipe.
```

## 例 2

```js
// Node.js program to demonstrate the
// stats.isFIFO() Method

// Accessing fs module
const fs = require('fs').promises;

// Calling isFIFO() method from
// fs.Stats class
(async () => {
    const stat = await fs.lstat('./');
    console.log(stat.isFIFO());
})().catch(console.error)
```

**输出:**

```js
false
```

**注意:** 以上程序使用 `node filename.js` 命令编译运行，正确使用 `file_path`。

**参考资料:** [https://nodejs.org/api/fs.html#fs_stats_isfifo](https://nodejs.org/api/fs.html#fs_stats_isfifo)