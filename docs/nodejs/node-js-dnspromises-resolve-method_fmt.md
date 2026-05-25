# Node.js dnsPromises.resolve()方法

> 原文：[https://www.geeksforgeeks.org/node-js-dnspromises-resolve-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolve-method/)

`dnsPromises.resolve()`方法是`dns`模块Promises对象的内置应用程序编程接口，用于将主机名解析为资源记录数组。

## 语法

```js
dnsPromises.resolve( hostname, rrtype )
```

## 参数

该方法有两个参数，如下所述：

*   `hostname`：此参数指定一个字符串，表示要解析的主机名。
*   `rrtype`：指定资源记录类型。其默认值为`"a"`。可选值包括`a`、`AAAA`、`ANY`、`CNAME`、`MX`、`TXT`、`NS`、`NAPTR`、`PTR`、`SOA`和`SRV`。
    *   `A`：IPv4地址记录。
    *   `AAAA`：IPv6地址记录。
    *   `ANY`：任意记录。
    *   `CNAME`：规范名称记录。
    *   `MX`：邮件交换记录。
    *   `TXT`：文本记录。
    *   `NS`：名称服务器记录。
    *   `NAPTR`：命名权威指针记录。
    *   `PTR`：指针记录。
    *   `SOA`：授权起始记录。
    *   `SRV`：服务定位记录。

## 返回值

此方法返回一个Promise，其解析值为资源记录数组，或者在出错时拒绝。

下面的例子说明了`dnsPromises.resolve()`方法在Node.js中的使用：

## 例 1

```js
// Node.js program to demonstrate the
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype value for
// dnsPromises.resolve() method
const rrtype="NS";

// Calling dnsPromises.resolve() method
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出：**

```js
[ 'ns-869.awsdns-44.net',
  'ns-245.awsdns-30.com',
  'ns-1520.awsdns-62.org',
  'ns-1569.awsdns-04.co.uk' ]
```

## 例 2

```js
// Node.js program to demonstrate the
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Setting rrtype for dnsPromises.resolve() method
const rrtype = "MX";

// Calling dnsPromises.resolve() method asynchronously
(async function() {

// Records from resolve function
    const records = await dnsPromises.resolve('geeksforgeeks.org', rrtype);

// Printing  records
    console.log("from async: ");
    console.log(records);
})();
```

**输出：**

```js
from async:
[ { exchange: 'alt2.aspmx.l.google.com', priority: 5 },
  { exchange: 'aspmx.l.google.com', priority: 1 },
  { exchange: 'alt3.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt4.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt1.aspmx.l.google.com', priority: 5 }
]
```

## 例 3

```js
// Node.js program to demonstrate the
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype for dnsPromises.resolve() method
const rrtype = "A";

// Calling dnsPromises.resolve() method
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出：**

```js
[ '34.218.62.116' ]
```

## 例 4

```js
// Node.js program to demonstrate the
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype for dnsPromises.resolve() method
const rrtype = "TXT";

// Calling dnsPromises.resolve() method
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出：**

```js
(node:12752) ExperimentalWarning: The dns.promises API is experimental
[ [ 'v=spf1 include:amazonses.com include:_spf.google.com -all' ],
  [ 'fob1m1abcdp777bf2ncvnjm08n' ] ]
```

## 注意

以上程序使用`node index.js`命令编译运行。

## 参考

[https://nodejs.org/api/dns.html#dns_dnspromises_resolve_hostname_rrtype](https://nodejs.org/api/dns.html#dns_dnspromises_resolve_hostname_rrtype)