# Node.js OS.hostname()方法

> 原文：[https://www.geeksforgeeks.org/node-js-os-hostname-method/](https://www.geeksforgeeks.org/node-js-os-hostname-method/)

`os.hostname()`方法是`os`模块的内置应用编程接口，用于获取操作系统的主机名。

**语法：**

```js
os.hostname()
```

**参数：** 此方法不接受任何参数。

**返回值：** 这个方法返回一个字符串值，指定操作系统的主机名。

下面的例子说明了`os.hostname()`方法在Node.js中的使用：

**示例 1：**

```js
// Node.js program to demonstrate the os.hostname() method

// 导入 os 模块
const os = require('os');

// 打印 os.hostname() 的值
console.log(os.hostname());
```

**输出：**

```js
gekchos_lappy
```

**示例 2：**

```js
// Node.js program to demonstrate the os.hostname() method

// 导入 os 模块
const os = require('os');

// 打印 os.hostname() 的值
if(os.hostname()) {
    var hostname = os.hostname();
    console.log("Hostname for the operating"
        + " system is " + String(hostname));
}
```

**输出：**

```js
Hostname for the operating system is gekchos_lappy
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/api/os.html#os_os_hostname](https://nodejs.org/api/os.html#os_os_hostname)