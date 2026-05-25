# Node.js `fsPromises.rmdir()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-fspromises-rmdir-method/](https://www.geeksforgeeks.org/node-js-fspromises-rmdir-method/)

`fsPromises.rmdir()` 方法用于删除给定路径的目录。它也可以递归地用于移除嵌套目录。它返回一个承诺（Promise），成功后没有参数。

## 语法

```js
fsPromises.rmdir( path, options )
```

## 参数

该方法接受两个参数，如下所述：

*   **`path`**: 要删除的目录路径。可以是一个字符串、一个 Buffer 或一个 Web URL。
*   **`options`**: 一个对象，可用于指定影响操作的可选参数。它有三个可选参数：
    *   **`recursive`**: 一个布尔值，指定是否执行递归目录删除。在此模式下，如果找不到指定路径且操作因失败而重试，则不会报告错误。默认值为 `false`。
    *   **`maxRetries`**: 一个整数值，指定如果操作因任何错误而失败，Node.js 将尝试执行此操作的次数。操作在给定的重试延迟后执行。如果 `recursive` 选项未设置为 `true`，则忽略此选项。默认值为 `0`。
    *   **`retryDelay`**: 一个整数值，指定在重试操作之前等待的时间（以毫秒为单位）。如果 `recursive` 选项未设置为 `true`，则忽略此选项。默认值为 `100`。

下面的例子说明了 Node.js 中的 `fsPromises.rmdir()` 方法：

**注意：** 在机器路径中创建 `gfg_directory` 以正确运行代码。

## 示例 1

本示例使用 `fsPromises.rmdir()` 方法删除目录。

```js
// Node.js program to demonstrate the 
// fsPromises.rmdir() method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

// Get the current filenames 
// in the directory 
getCurrentFilenames();

(async function main() {
    try {
        await fsPromises.rmdir("gfg_directory");
        console.log("Folder Deleted!");

        // Get the current filenames 
        // in the directory to verify 
        getCurrentFilenames();
    } catch (err) {
        console.error(err);
    }
})();

// Function to get current filenames 
// in directory 
function getCurrentFilenames() {
    console.log("\nCurrent filenames:");
    fs.readdirSync(__dirname).forEach(file => {
        console.log(file);
    });
    console.log("\n");
}
```