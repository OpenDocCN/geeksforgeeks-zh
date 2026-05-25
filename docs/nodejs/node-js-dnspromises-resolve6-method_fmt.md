# Node.js dnsPromises.resolve6() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-dnspromises-resolve6-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolve6-method/)

`dnsPromises.resolve6()` 方法是 `dns` 模块承诺的内置应用程序编程接口，用于使用 DNS 协议解析指定主机名的 IPv6 地址（“AAAA”记录）。

## 语法

```js
dnsPromises.resolve6( hostname, options )
```

## 参数

该方法有两个参数，如下所述：

*   `hostname`: 此参数指定一个字符串，表示要解析的主机名。
*   `options`: 它是一个对象的形式。
    *   `ttl`: 是一个布尔参数，指定是否检索每条记录的生存时间值（TTL）。如果设置为 `true`，将检索每条记录的 TTL（以秒为单位）。

## 返回值

此方法返回错误，记录。

以下示例说明了在 Node.js 中使用该方法：

## 例 1

```js
// Node.js program to demonstrate the
// dnsPromises.resolve6() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolve6() method
dnsPromises.resolve6('geeksforgeeks.org').then((res) => {
    console.log(res);
});

// Calling dnsPromises.resolve6() method
// asynchronously
(async function() {

// Records from resolve6 function
    const records = await dnsPromises.resolve6('geeksforgeeks.org');

// Printing records
    console.log("from async: ");
    console.log(records);
})();
```

### 输出

```js
from async:
[ 'fd00:0:13:13::22da:3e74' ]
[ 'fd00:0:13:13::22da:3e74' ]
```

## 例 2

```js
// Node.js program to demonstrate the
// dnsPromises.resolve6() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.resolve6() method
const options={
    ttl:true,
};

// Calling dnsPromises.resolve6() method
// asynchronously
(async function() {

// Records from resolve6 function
    const records = await dnsPromises.resolve6(
                    'geeksforgeeks.org', options);

// Printing records
    console.log("from async: ");
    console.log(records);
})();
```

### 输出

```js
from async:
[ { address: 'fd00:0:13:13::22da:3e74', ttl: 30 } ]
```

**注意:** 以上程序使用 `node index.js` 命令编译运行。

**参考:** [https://nodejs.org/api/dns.html#dns_dnspromises_resolve6_hostname_options](https://nodejs.org/api/dns.html#dns_dnspromises_resolve6_hostname_options)