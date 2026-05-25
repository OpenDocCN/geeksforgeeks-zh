# Node.js dns.resolveNaptr()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-resolvenaptr-method/](https://www.geeksforgeeks.org/node-js-dns-resolvenaptr-method/)

`dns.resolveNaptr()`方法是`dns`模块的内置应用程序编程接口，用于使用`dns`协议解析指定主机名的`Naptr`记录或基于正则表达式的记录。

## 语法

```js
dns.resolveNaptr( hostname, callback )
```

## 参数

该方法有两个参数，如下所述：

*   `Hostname`: 此参数指定一个字符串，表示要解析的主机名。
*   `Callback`: 指定在主机名的 DNS 解析完成后要调用的函数。
    *   `Error`: 指定的生成错误。
    *   `Address`: 是一个字符串数组，表示返回的基于正则表达式的主机名记录。

## 返回值

此方法通过回调函数返回错误或地址。这些数据作为参数传递给回调函数。参数`address`将包含具有属性`flags`、`service`、`regexp`、`replacement`、`order`和`preference`的对象数组。

以下示例说明了`dns.resolveNaptr()`在 Node.js 中的方法：

## 示例 1

```js
// Node.js program to demonstrate the
// dns.resolveNaptr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveNaptr() method for
// hostname geeksforgeeks.org and displaying
// them in console as a callback
dns.resolveNaptr('geeksforgeeks.org', (err,
    addresses) => console.log('naptr records: %j', addresses));
```

**输出:**

```js
QueryReqWrap {
  bindingName: 'queryNaptr',
  callback: [Function],
  hostname: 'geeksforgeeks.org',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
naptr records: undefined
```

**注意:** 以上程序使用`node index.js`命令编译运行。

**参考:** [https://nodejs.org/api/dns.html#dns_dns_resolvenaptr_hostname_callback](https://nodejs.org/api/dns.html#dns_dns_resolvenaptr_hostname_callback)