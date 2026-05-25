# Node.js 中的 `fs.Stats.isCharacterDevice()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-stats-ischaracterdevice-method-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-ischaracterdevice-method-from-fs-stats-class/)

`stats.isCharacterDevice()` 方法是 `fs` 内置模块的 API。用于检查 `fs.Stats` 对象是否描述一个字符设备。

## 语法

```js
stats.isCharacterDevice();
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个布尔值，如果 `fs.Stats` 对象描述字符设备则为 `true`，否则为 `false`。

下面的例子说明了 `stats.isCharacterDevice()` 方法在 Node.js 中的使用:

## 例 1

```js
// Node.js program to demonstrate the
// stats.isCharacterDevice() Method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isCharacterDevice() method
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isCharacterDevice());
});
```

**输出:**

```js
false
```

## 例 2

```js
// Node.js program to demonstrate the
// stats.isCharacterDevice() Method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isCharacterDevice() method
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    // console.log(`stats: ${JSON.stringify(stats)}`);

    if (stats.isCharacterDevice()) {
        console.log("fs.Stats describes a "
                + "character device");
    } else {
        console.log("fs.Stats does not "
            + "describe a character device");
    }
});
```

**输出:**

```js
fs.Stats does not describe a character device
```

**注意:** 以上程序使用 `node filename.js` 命令编译运行，需正确使用 `file_path`。

**参考:** [https://nodejs.org/api/fs.html#fs_stats_ischaracterdevice](https://nodejs.org/api/fs.html#fs_stats_ischaracterdevice)