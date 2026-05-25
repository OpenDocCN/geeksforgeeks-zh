# Node.js `process.getuid()`方法

> 原文: [https://www.geeksforgeeks.org/node-js-process-getuid-method/](https://www.geeksforgeeks.org/node-js-process-getuid-method/)

`process.getuid()`方法是`process`模块的内置应用编程接口，用于获取 Node.js 进程的数字用户标识。

## 语法

```js
process.getuid()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个整数值，指定 Node.js 进程的数字用户标识。

## 注意

这个方法只会在 POSIX 平台上工作。在 Windows 或 Android 平台上不可用，因此会导致错误，即 `TypeError: getuid is not a function`。

下面的例子说明了 `process.getuid()`方法在 Node.js 中的使用:

### 例 1

```js
// Node.js program to demonstrate the     
// process.getuid() method

// Include process module
const process = require('process');

// Printing the numerical user 
// identity of the Node.js process
console.log(process.getuid());
```

**输出:**

```js

```

### 例 2

```js
// Node.js program to demonstrate the     
// process.getuid() method

// Include process module
const process = require('process');

// Check whether the method exists or not
if (process.getuid) {

  // Printing getuid() value
  console.log("The numerical user identity "
            + "of the Node.js process: "
            + process.getuid());
}
```

**输出:**

```js
The numerical user identity of the Node.js process: 6693036
```

**注意:** 以上程序使用 `node filename.js` 命令编译运行。

**参考:** [https://nodejs.org/api/process.html#process_process_getuid](https://nodejs.org/api/process.html#process_process_getuid)