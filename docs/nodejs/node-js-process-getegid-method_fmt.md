# Node.js process.getegid()方法

> 原文: [https://www.geeksforgeeks.org/node-js-process-getegid-method/](https://www.geeksforgeeks.org/node-js-process-getegid-method/)

## 方法介绍

`process.getegid()`方法是`process`模块的内置应用编程接口，用于获取 Node.js 进程的数字有效组标识。

## 语法

```js
process.getegid()
```

## 参数

此方法不接受任何参数。

## 返回值

返回一个指定 Node.js 进程的数字有效组标识的对象。

## 注意

此功能仅在 POSIX 平台上有效。在 Windows 或 Android 平台上不可用，因此会导致错误，即 `TypeError: getegid is not a function`。

下面的例子说明了 `process.getegid()`方法在 Node.js 中的使用。

## 示例 1

```js
// Node.js program to demonstrate the
// process.getegid() Method

// Include process module
const process = require('process');

// Print the numerical effective group
// identity of the Node.js process
console.log(process.getegid());
```

**输出:**

```js

```

## 示例 2

```js
// Node.js program to demonstrate the
// process.getegid() Method

// Include process module
const process = require('process');

// Check whether the method exists or not
if (process.getegid) {

  // Printing getegid() value
  console.log("The numerical effective group"
        + " identity of the Node.js process:"
        + process.getegid());
}
```

**输出:**

```js
The numerical effective group identity of the Node.js process: 0
```

**注意:** 以上程序使用 `node filename.js` 命令编译运行。

**参考:** [https://nodejs.org/api/process.html#process_process_getegid](https://nodejs.org/api/process.html#process_process_getegid)