# Node.js process.platform 属性

> 原文: [https://www.geeksforgeeks.org/node-js-process-platform-property/](https://www.geeksforgeeks.org/node-js-process-platform-property/)

`process.platform` 属性是 `process` 模块的内置 API，用于获取操作系统平台信息。

**语法:**

```js
process.platform
```

**返回值:** 这个属性返回一个代表操作系统平台的字符串。返回值可以是 `"aix"`、`"android"`、`"darwin"`、`"freebsd"`、`"linux"`、`"openbsd"`、`"sunos"` 和 `"win32"` 中的一个。该值在编译时设置。

下面的例子说明了 `process.platform` 属性在 Node.js 中的使用:

## 例 1

```js
// Node.js program to demonstrate the
// process.platform Property

// Include process module
const process = require('process');

// Printing process.platform property value
console.log(process.platform);
```

**输出:**

```js
win32
```

## 例 2

```js
// Node.js program to demonstrate the
// process.platform Property

// Include process module
const process = require('process');

// Printing process.platform property value
var platform = process.platform;
switch(platform) {
    case 'aix': 
        console.log("IBM AIX platform");
        break;
    case 'darwin': 
        console.log("Darwin platform(MacOS, IOS etc)");
        break;
    case 'freebsd': 
        console.log("FreeBSD Platform");
        break;
    case 'linux': 
        console.log("Linux Platform");
        break;
    case 'openbsd': 
        console.log("OpenBSD platform");
        break;
    case 'sunos': 
        console.log("SunOS platform");
        break;
    case 'win32':
        console.log("windows platform");
        break;    
    default: 
        console.log("unknown platform");
}
```

**输出:**

```js
windows platform
```

**注意:** 以上程序将使用 `node filename.js` 命令编译运行。
**参考:** [https://nodejs.org/api/process.html#process_process_platform](https://nodejs.org/api/process.html#process_process_platform)