# Node.js `process.seteuid()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-process-seteuid-method/](https://www.geeksforgeeks.org/node-js-process-seteuid-method/)

`process.seteuid()` 方法是 `process` 模块的内置 API，用于设置 Node.js 进程的有效用户标识。

## 语法

```js
process.seteuid( id )
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `id`: 它是一个必需的参数，包含一个字符串或一个整数，表示数字 id 或用户名字符串。如果传递了用户名，它会在解析相关数字标识时阻塞。

## 返回值

不返回值。

## 注意

此功能仅在 POSIX 平台上有效。它在 Windows 或 Android 平台上不可用，因此会导致错误，即 `TypeError: seteuid is not a function`。

下面的例子说明了 `process.seteuid()` 方法在 Node.js 中的使用：

## 示例

### 例 1

```js
// Node.js program to demonstrate the     
// process.seteuid() method

// Include process module
const process = require('process');

// Printing the effective user identity
// of the Node.js process and checking
// whether the method exists or not
if (process.geteuid && process.seteuid ) {

// Setting user id
  process.seteuid(400);

// Printing geteuid()
  console.log("The effective user identity "
        + "of the Node.js process:"
        + process.geteuid());
}
```

**输出:**

```js
The effective user identity of the Node.js process: 400
```

### 例 2

```js
// Node.js program to demonstrate the     
// process.seteuid() method

// Include process module
const process = require('process');

// Set user id and checking whether
// the method exists or not
if (process.seteuid) {

// Within try catch
  try {
      process.seteuid(696);
      console.log("User id has successfully been set");
  } catch (err) {
      console.log("Failed to set user id:", err);
  }
}

// Checking whether the method exists or not
if (process.geteuid) {

// Printing geteuid() value
    console.log("The numerical effective user "
          + "identity of the Node.js process:"
          + process.geteuid());
}
```

**输出:**

```js
User id has successfully been set
The numerical effective user identity of the Node.js process: 696
```

**注意:** 以上程序将使用 `node filename.js` 命令编译运行。

**参考:** [https://nodejs.org/api/process.html#process_process_seteuid_id](https://nodejs.org/api/process.html#process_process_seteuid_id)