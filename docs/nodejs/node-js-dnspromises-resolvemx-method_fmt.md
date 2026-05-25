# `dnsPromises.resolveMx()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-dnspromises-resolvemx-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolvemx-method/)

`dnsPromises.resolveMx()` 方法是 `dns` 模块 `Promises` 对象的内置应用编程接口，用于使用 DNS 协议解析指定主机名的 MX（邮件交换）记录。

## 语法

```js
dnsPromises.resolveMx( hostname )
```

## 参数

该方法接受一个参数，如下所述：

*   `hostname`：此参数指定一个字符串，表示要解析的主机名。

## 返回值

这个方法返回错误或地址。

## 示例

下面的例子说明了该方法在 Node.js 中的使用：

### 例 1

```js
// Node.js program to demonstrate the
// dnsPromises.resolveMx() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveMx() method
dnsPromises.resolveMx('google.com').then((res) => {
    console.log("for google : ");
    console.log(res);
});
```

**输出：**

```js
for google :
[ { exchange: 'alt4.aspmx.l.google.com', priority: 50 },
  { exchange: 'alt3.aspmx.l.google.com', priority: 40 },
  { exchange: 'aspmx.l.google.com', priority: 10 },
  { exchange: 'alt1.aspmx.l.google.com', priority: 20 },
  { exchange: 'alt2.aspmx.l.google.com', priority: 30 } ]
```

### 例 2

```js
// Node.js program to demonstrate the
// dnsPromises.resolveMx() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveMx() method
// asynchronously
(async function() {

// Records from resolveMx function
    const records = await dnsPromises.resolveMx(
                        'geeksforgeeks.org');

// Printing records
    console.log("from async: ");
    console.log(records);
})();
```

**输出：**

```js
from async:
[ { exchange: 'aspmx.l.google.com', priority: 1 },
  { exchange: 'alt3.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt4.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt1.aspmx.l.google.com', priority: 5 },
  { exchange: 'alt2.aspmx.l.google.com', priority: 5 } ]
```

**注意：** 以上程序使用 `node index.js` 命令编译运行。

**参考：** [https://nodejs.org/api/dns.html#dns_dnspromises_resolvemx_hostname](https://nodejs.org/api/dns.html#dns_dnspromises_resolvemx_hostname)