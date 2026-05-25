# Node.js path.delimiter 属性

> 原文：[https://www.geeksforgeeks.org/node-js-path-delimiter-property/](https://www.geeksforgeeks.org/node-js-path-delimiter-property/)

`path.delimiter` 属性是 `path` 模块的内置 API，用于获取平台特定的路径分隔符。

**语法：**

```js
path.delimiter;
```

**返回值：** 该属性返回一个表示平台特定路径分隔符的字符串。返回值为 `:` 为 POSIX，`;` 为 Windows。

下面的例子说明了 `path.delimiter` 在 Node.js 中的使用：

**例 1：**

```js
// Node.js program to demonstrate the
// path.delimiter property

// Allocating path module
const path = require('path');

// Printing path.delimiter value
console.log(path.delimiter);
```

**输出：**

```js
;
```

**例 2：**

```js
// Node.js program to demonstrate the
// path.delimiter property

// Allocating path module
const path = require('path');

// Allocating process module
const process = require('process');

// Printing path.delimiter value
var delimiter = path.delimiter;

console.log(process.env.PATH);
console.log(process.env.PATH.split(path.delimiter));
```

**输出：**

```js
C:\wamp64\bin\php\php7.3.1\ext\ImageMagick;C:\Program Files (x86)\Common 
Files\Oracle\Java\javapath;C:\Windows\system32;C:\Windows;
C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;
C:\Windows\System32\OpenSSH\;D:\programfiles\Git\cmd;
D:\programfiles\Cmake\bin;
C:\Program
Files\nodejs\;C:\Users\gekcho\AppData\Local\Microsoft\WindowsApps;
C:\Users\gekcho\AppData\Roaming\npm
[ 'C:\\wamp64\\bin\\php\\php7.3.1\\ext\\ImageMagick',
  'C:\\Program Files (x86)\\Common Files\\Oracle\\Java\\javapath',
  'C:\\Windows\\system32',
  'C:\\Windows',
  'C:\\Windows\\System32\\Wbem',
  'C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\',
  'C:\\Windows\\System32\\OpenSSH\\',
  'D:\\programfiles\\Git\\cmd',
  'D:\\programfiles\\Cmake\\bin',
  'C:\\Program Files\\nodejs\\',
  'C:\\Users\\gekcho\\AppData\\Local\\Microsoft\\WindowsApps',
  'C:\\Users\\gekcho\\AppData\\Roaming\\npm' ]
```

**注意：** 以上程序使用 `node filename.js` 命令编译运行。

**参考：** [https://nodejs.org/api/path.html#path_path_delimiter](https://nodejs.org/api/path.html#path_path_delimiter)