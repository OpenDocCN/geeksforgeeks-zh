# Node.js dns.resolvePtr()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-resolveptr-method/](https://www.geeksforgeeks.org/node-js-dns-resolveptr-method/)

`dns.resolvePtr()`方法是`dns`模块的内置应用编程接口，用于使用`dns`协议解析指定主机名的`Ptr`或指针记录。

## 语法:

```js
dns.resolvePtr( hostname, callback )
```

## 参数:

该方法有两个参数，如下所述：

*   `Hostname`: 此参数指定一个表示要解析的主机名的字符串。
*   `Callback`: 指定在主机名的DNS解析完成后要调用的函数。
    *   `Error`: 指定生成的错误。
    *   `Address`: 是一个字符串数组，表示返回的主机名指针记录。

## 返回值:

此方法通过回调函数返回错误和地址数据。这些数据作为参数传递给回调函数。

以下示例说明了`dns.resolvePtr()`方法在Node.js中的使用：

## 例 1:

```js
// Node.js program to demonstrate the   
// dns.resolvePtr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolvePtr() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolvePtr('geeksforgeeks.org', (err, 
    addresses) => console.log('PTR records: %j', addresses));
```

## 输出:

```js
PTR records:[{"34.218.62.116"}]
```

## 例 2:

```js
// Node.js program to demonstrate the   
// dns.resolvePtr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolvePtr() method for hostname
// google.com and displaying them in
// console as a callback
dns.resolvePtr('google.com', (err, 
    addresses) => console.log('PTR records: %j', addresses));
```

## 输出:

```js
PTR records:[{"172.217.164.142"}]
```

## 注意:

以上程序使用`node index.js`命令编译运行。

## 参考:

[https://nodejs.org/api/dns.html#dns_dns_resolveptr_hostname_callback](https://nodejs.org/api/dns.html#dns_dns_resolveptr_hostname_callback)