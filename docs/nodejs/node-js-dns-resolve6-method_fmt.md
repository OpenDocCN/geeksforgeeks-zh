# Node.js dns.resolve6()方法

> 原文：[https://www.geeksforgeeks.org/node-js-dns-resolve6-method/](https://www.geeksforgeeks.org/node-js-dns-resolve6-method/)

`dns.resolve6()`方法是`dns`模块的内置应用程序编程接口，用于使用`dns`协议解析指定主机名的IPv6地址（“AAAA”记录）。

## 语法：
```js
dns.resolve6( hostname, options, callback )
```

## 参数：
该方法接受三个参数，如下所述：

*   `hostname`：此参数指定一个字符串，表示要解析的主机名。
*   `options`：它是一个对象形式。
    *   `ttl`：它是一个布尔参数，指定是否检索每条记录的生存时间值（TTL）。如果设置为`true`，将检索每条记录的TTL（以秒为单位）。
*   `callback`：指定在主机名DNS解析后要调用的函数。
    *   `error`：指定的生成错误。
    *   `address`：它是一个字符串或对象，表示为主机名返回的IPv6地址。

## 返回值：
该方法通过回调函数返回IPv6地址。这些数据作为参数传递给回调函数。

下面的例子说明了`dns.resolve6()`方法在Node.js中的使用：

## 例 1：
```js
// Node.js program to demonstrate the
// dns.resolve6() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolve6() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolve6('geeksforgeeks.org', (err,
    address) => console.log('address: %j', address));
```

**输出：**
```js
address: ["fd00:0:14:13::22da:3e74"]
```

## 例 2：
```js
// Node.js program to demonstrate the
// dns.resolve6() method

// Accessing dns module
const dns = require('dns');

// Set the options for dns.resolve6() method
const options = {
    ttl : true
};

// Calling dns.resolve6() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolve6('geeksforgeeks.org', options, (err,
    address) => console.log('address: %j', address));
```

**输出：**
```js
address: [{"address":"fd00:0:14:13::22da:3e74", "ttl":30}]
```

### 注意：
以上程序使用`node index.js`命令编译运行。

### 参考：
[https://nodejs.org/api/dns.html#dns_dns_resolve6_hostname_options_callback](https://nodejs.org/api/dns.html#dns_dns_resolve6_hostname_options_callback)