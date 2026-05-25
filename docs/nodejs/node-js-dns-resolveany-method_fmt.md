# Node.js dns.resolveAny()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-resolveany-method/](https://www.geeksforgeeks.org/node-js-dns-resolveany-method/)

`dns.resolveAny()`方法是`dns`模块的内置应用编程接口，用于使用`dns`协议解析指定主机名的所有记录(即“Any”或“*”)。

## 语法

```js
dns.resolveAny( hostname, callback )
```

## 参数

该方法有两个参数，如下所述：

*   `Hostname`: 此参数指定一个字符串，表示要解析的主机名。
*   `Callback`: 指定在主机名的DNS解析完成后要调用的函数。
    *   `Error`: 指定生成的错误。
    *   `ret`: 一个对象，表示主机名的返回记录。

## 返回值

此方法返回错误，通过回调函数记录。这些数据作为参数传递给回调函数。

可以返回的记录有：

*   `A`: IPv4 地址
*   `AAAA`: IPv6 地址
*   `ANY`: 任意记录
*   `CNAME`: 别名记录
*   `MX`: 邮件交换记录
*   `NAPTR`: 名称权限指针记录
*   `NS`: 名称服务器记录
*   `PTR`: 指针记录
*   `SOA`: 权威记录的开始
*   `SRV`: 服务记录
*   `TXT`: 文本记录

下面的例子说明了在Node.js中`dns.resolveAny()`方法的使用：

## 例 1

```js
// Node.js program to demonstrate the
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveAny() method for
// hostname geeksforgeeks.org and displaying
// them in console as a callback
dns.resolveAny('geeksforgeeks.org', (err,
    ret) => console.log('records: %j', ret));
```

**输出:**

```js
records: [
    {"value":"ns-1520.awsdns-62.org","type":"NS"},
    {"value":"ns-1569.awsdns-04.co.uk","type":"NS"},
    {"value":"ns-245.awsdns-30.com","type":"NS"},
    {"value":"ns-869.awsdns-44.net","type":"NS"}
]
```

## 例 2

```js
// Node.js program to demonstrate the
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveAny() method for
// hostname localhost and displaying
// them in console as a callback
dns.resolveAny('localhost', (err,
    ret) => console.log('records: %j', ret));
```

**输出:**

```js
records: [
    {"address":"127.0.0.1", "ttl":0, "type":"A"}
]
```

**注意:** 以上程序使用`node index.js`命令编译运行。

**参考:** [https://nodejs.org/api/dns.html#dns_dns_resolveany_hostname_callback](https://nodejs.org/api/dns.html#dns_dns_resolveany_hostname_callback)