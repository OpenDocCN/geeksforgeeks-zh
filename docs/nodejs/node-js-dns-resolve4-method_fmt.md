# Node.js dns.resolve4()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-resolve4-method/](https://www.geeksforgeeks.org/node-js-dns-resolve4-method/)

`dns.resolve4()`方法是 `dns` 模块的内置应用程序编程接口，用于使用 `dns` 协议解析指定主机名的 IPv4 地址(“A”记录)。

## 语法:

```js
dns.resolve4( hostname, options, callback )
```

## 参数:

该方法接受三个参数，如下所述:

*   `Hostname`: 此参数指定一个字符串，表示要解析的主机名。
*   `Option`: 它是一个对象的形式。
    *   `ttl`: 这是一个布尔参数，指定是否检索每条记录的生存时间值(TTL)。如果设置为 `true`，将检索每条记录的 TTL（以秒为单位）。
*   `Callback`: 指定在主机名 DNS 解析后要调用的函数。
    *   `Error`: 指定生成的错误。
    *   `Address`: 是一个字符串或对象，表示返回的主机名的 IPv4 地址。

## 返回值:

该方法通过回调函数返回错误、地址。这些数据作为参数传递给回调函数。

以下示例说明了在 Node.js 中 `dns.resolve4()`方法的使用:

## 例 1:

```js
// Node.js program to demonstrate the   
// dns.resolve4() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolve4() method for hostname
// geeksforgeeks.org and display them in
// console as a callback
dns.resolve4('geeksforgeeks.org', (err,
    address) => console.log('address: %j', address));
```

**输出:**

```js
address: ["34.218.62.116"]
```

## 例 2:

```js
// Node.js program to demonstrate the   
// dns.resolve4() method

// Accessing dns module
const dns = require('dns');

// Setting options value for
// dns.resolve4() method
const options = {
    ttl: true,
};

// Calling dns.resolve4() method for hostname
// geeksforgeeks.org and displaying them
// in console as a callback
dns.resolve4('geeksforgeeks.org', options, (err,
    address) => console.log('address: %j', address));
```

**输出:**

```js
address: [{"address":"34.218.62.116", "ttl":9}]
```

## 注意:

以上程序使用 `node index.js` 命令编译运行。

## 参考:

[https://nodejs.org/api/dns.html#dns_dns_resolve4_hostname_options_callback](https://nodejs.org/api/dns.html#dns_dns_resolve4_hostname_options_callback)