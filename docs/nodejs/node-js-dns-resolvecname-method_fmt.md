# Node.js dns.resolveCname()方法

> 原文：`https://www.geeksforgeeks.org/node-js-dns-resolvecname-method/`

## dns.resolveCname()方法

`dns.resolveCname()`方法是`dns`模块的内置应用程序编程接口，用于使用`dns`协议解析指定主机名的Cname记录。

## 语法

```js
dns.resolveCname( hostname, callback )
```

## 参数

该方法有两个参数，如上所述，如下所述：

*   `Hostname`：此参数指定一个字符串，表示要解析的主机名。
*   `Callback`：指定在主机名的DNS解析完成后要调用的函数。
    *   `Error`：指定的生成错误。
    *   `Address`：它是一个字符串数组，表示返回的主机名cname地址。

## 返回值

这个方法通过回调函数返回错误、地址，这些数据作为参数传递给回调函数。

下面的例子说明了在Node.js中使用`dns.resolveCname()`方法：

### 例1

```js
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveCname() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveCname('geeksforgeeks.org', (err, 
    addresses) => console.log('addresses: %j', addresses));
```

**输出：**

```js
QueryReqWrap {
  bindingName: 'queryCname',
  callback: [Function],
  hostname: 'geeksforgeeks.org',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
addresses: undefined
```

### 例2

```js
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveCname() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveCname('localhost', (err, 
    addresses) => console.log('addresses: %j', addresses));
```

**输出：**

```js
QueryReqWrap {
  bindingName: 'queryCname',
  callback: [Function],
  hostname: 'localhost',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
addresses: undefined
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** `https://nodejs.org/api/dns.html#dns_dns_resolvecname_hostname_callback`