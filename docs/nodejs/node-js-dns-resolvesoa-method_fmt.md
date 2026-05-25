# Node.js dns.resolveSoa()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-resolvesoa-method/](https://www.geeksforgeeks.org/node-js-dns-resolvesoa-method/)

## dns.resolveSoa()方法

`dns.resolveSoa()`方法是`dns`模块的内置应用程序编程接口，用于使用`dns`协议解析指定主机名的 Soa 或权限记录的开始。

## 语法

```js
dns.resolveSoa( hostname, callback )
```

## 参数

该方法有两个参数，如下所述：

*   **Hostname:** 此参数指定一个字符串，表示要解析的主机名。
*   **Callback:** 指定在主机名的 DNS 解析完成后要调用的函数。
    *   **Error:** 指定的生成错误。
    *   **Address:** 一个字符串数组，表示返回的主机名的授权开始（SOA）记录。

## 返回值

此方法返回错误，通过回调函数寻址。这些数据作为参数传递给回调函数。`address`参数将包含`nsname`、`hostmaster`、`serial`、`refresh`、`retry`、`expire`和`minttl`属性。

下面的例子说明了在 Node.js 中`dns.resolveSoa()`方法的使用：

## 例 1

```js
// Node.js program to demonstrate the   
// dns.resolveSoa() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveSoa() method for hostname
//  geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveSoa('geeksforgeeks.org', (err, 
    addresses) => console.log('SOA records: %j', addresses));
```

**输出:**

```js
SOA records: {
    "nsname":"ns-869.awsdns-44.net",
    "hostmaster":"awsdns-hostmaster.amazon.com",
    "serial":1,
    "refresh":7200,
    "retry":900,
    "expire":1209600,
    "minttl":86400
}
```

## 例 2

```js
// Node.js program to demonstrate the   
// dns.resolveSoa() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveSoa() method for hostname
// google.com printing them in console as a callback
dns.resolveSoa('google.com', (err, 
    addresses) => console.log('SOA records: %j', addresses));
```

**输出:**

```js
SOA records: {
    "nsname":"ns1.google.com",
    "hostmaster":"dns-admin.google.com",
    "serial":287530106,
    "refresh":900,
    "retry":900,
    "expire":1800,
    "minttl":60
}
```

## 注意

以上程序使用`node index.js`命令编译运行。

## 参考

[https://nodejs.org/api/dns.html#dns_dns_resolvesoa_hostname_callback](https://nodejs.org/api/dns.html#dns_dns_resolvesoa_hostname_callback)