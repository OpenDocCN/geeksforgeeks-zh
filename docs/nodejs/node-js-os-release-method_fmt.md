# Node.js os.release()方法

> 原文: [https://www.geeksforgeeks.org/node-js-os-release-method/](https://www.geeksforgeeks.org/node-js-os-release-method/)

`os.release()`方法是`os`模块的内置应用编程接口，用于获取操作系统版本。

## 语法

```js
os.release()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个代表操作系统版本的字符串。

下面的例子说明了`os.release()`方法在Node.js中的使用:

### 例 1

## JavaScript

```js
// Node.js program to demonstrate the os.release() method

// Allocating os module
const os = require('os');

// Printing os.release() value
console.log(os.release());
```

**输出:** 在windows系统上

```js
10.0.17763
```

**输出:** 在Linux系统上

```js
3.10.0-1062.1.1.el7.x86_64
```

### 例 2

## JavaScript

```js
// Node.js program to demonstrate the os.release() method

// Allocating os module
const os = require('os');

// Printing os.platform() value
var platform = os.platform();
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
        console.log("Windows platform");
        break;    
    default: 
        console.log("Unknown platform");
}

// Printing version 
console.log("Version: " + os.release());
```

**输出:**

```js
Windows platform
Version: 10.0.17763
```

**注意:** 以上程序将使用`node index.js`命令编译运行。

**参考:** [https://nodejs.org/api/os.html#os_os_release](https://nodejs.org/api/os.html#os_os_release)