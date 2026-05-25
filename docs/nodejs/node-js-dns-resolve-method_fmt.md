# Node.js `dns.resolve()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-dns-resolve-method/](https://www.geeksforgeeks.org/node-js-dns-resolve-method/)

`dns.resolve()` 方法是 `dns` 模块的内置应用程序编程接口，用于将主机名解析为资源记录数组。

## 语法

```js
dns.resolve( hostname, rrtype, callback )
```

## 参数

该方法接受三个参数，如下所述：

*   `hostname`：该参数指定一个字符串，表示要解析的主机名。
*   `rrtype`：指定资源记录类型。它的默认值是 `"A"`。记录列表（`"A"`、`"AAAA"`、`"ANY"`、`"CNAME"`、`"MX"`、`"TXT"`、`"NS"`、`"NAPTR"`、`"PTR"`、`"SOA"`、`"SRV"`）描述如下：
    *   `"A"`：IPv4 地址
    *   `"AAAA"`：IPv6 地址
    *   `"ANY"`：任意记录
    *   `"CNAME"`：规范名称记录
    *   `"MX"`：邮件交换记录
    *   `"NAPTR"`：命名 authority 指针记录
    *   `"NS"`：名称服务器记录
    *   `"PTR"`：指针记录
    *   `"SOA"`：授权记录的开始
    *   `"SRV"`：服务记录
    *   `"TXT"`：文字记录
*   `callback`：指定一个在主机名 DNS 解析完成后调用的函数。
    *   `err`：如果生成，则指定错误。
    *   `records`：表示返回记录的字符串或对象。

## 返回值

这个方法通过回调函数返回 `err` 和 `records`，这些数据作为参数传递给回调函数。

下面的例子说明了在 Node.js 中使用 `dns.resolve()` 方法：

### 例 1

```js
// Node.js program to demonstrate the
// dns.resolve() method

// Accessing dns module
const dns = require('dns');

// Set the rrtype for dns.resolve() method
const rrtype = "A";

// Calling dns.resolve() method for hostname
// geeksforgeeks.org and print them in
// console as a callback
dns.resolve('geeksforgeeks.org', rrtype, (err, records)
    => console.log('records: %j', records));
```

**输出：**

```js
records: ["34.218.62.116"]
```

### 例 2

```js
// Node.js program to demonstrate the
// dns.resolve() method

// Accessing dns module
const dns = require('dns');

// Set the rrtype for dns.resolve() method
const rrtype = "MX";

// Calling dns.resolve() method for hostname
// geeksforgeeks.org and print them in
// console as a callback
dns.resolve('geeksforgeeks.org', rrtype, (err, records)
    => console.log('records: %j', records));
```

**输出：**

```js
records: [
    {"exchange":"alt1.aspmx.l.google.com", "priority":5},
    {"exchange":"alt2.aspmx.l.google.com", "priority":5},
    {"exchange":"aspmx.l.google.com", "priority":1},
    {"exchange":"alt3.aspmx.l.google.com", "priority":10},
    {"exchange":"alt4.aspmx.l.google.com", "priority":10}
]
```

### 例 3

```js
// Node.js program to demonstrate the
// dns.resolve() method

// Accessing dns module
const dns = require('dns');

// Set the rrtype for dns.resolve() method
const rrtype = "TXT";

// Calling dns.resolve() method for hostname
// geeksforgeeks.org and print them in
// console as a callback
dns.resolve('geeksforgeeks.org', rrtype, (err,
    records) => console.log('records: %j', records));
```

**输出：**

```js
records: [
    ["v=spf1 include:amazonses.com include:_spf.google.com -all"],
    ["fob1m1abcdp777bf2ncvnjm08n"]
]
```

### 例 4

```js
// Node.js program to demonstrate the
// dns.resolve() method

// Accessing dns module
const dns = require('dns');

// Set the rrtype for dns.resolve() method
const rrtype = "NS";

// Calling dns.resolve() method for hostname
// geeksforgeeks.org and print them in
// console as a callback
dns.resolve('geeksforgeeks.org', rrtype, (err,
    records) => console.log('records: %j', records));
```

**输出：**

```js
records: [
    "ns-1520.awsdns-62.org",
    "ns-1569.awsdns-04.co.uk",
    "ns-245.awsdns-30.com",
    "ns-869.awsdns-44.net"
]
```

**注意：** 以上程序使用 `node index.js` 命令编译运行。

**参考：** [https://nodejs.org/api/dns.html#dns_dns_resolve_hostname_rrtype_callback](https://nodejs.org/api/dns.html#dns_dns_resolve_hostname_rrtype_callback)