# Node.js dnsPromises.lookup()方法

> 原文：[https://www.geeksforgeeks.org/node-js-dnspromises-lookup-method/](https://www.geeksforgeeks.org/node-js-dnspromises-lookup-method/)

`dnsPromises.lookup()`方法是`dns`模块`Promises`对象的内置应用编程接口，用于将给定参数的指定主机名的IP地址解析为第一个找到的A (IPv4)或AAAA (IPv6)记录。

## 语法

```js
dnsPromises.lookup( hostname, options )
```

## 参数

该方法有两个参数，如下所述：

1.  `hostname`：此参数指定一个字符串，表示要检查的主机名。
2.  `options`：它是一个整数或对象形式。它指定在查找过程中要使用的选项。
    *   `family`：是指定记录族的整数值。其值必须在4、6或0之间，其中0表示返回IPv4和IPv6，4表示返回IPv4，6表示返回IPv6。默认值为0。
    *   `hints`：是一个数字，指定一个或多个`getaddrinfo`标志。可以通过对其值进行按位或（OR）来传递多个标志。
    *   `all`：它是一个布尔参数。如果设置为`true`，回调函数将返回数组中所有已解析的地址；否则，它返回单个地址。其默认值为`false`。
    *   `verbatim`：是一个布尔参数。如果设置为`true`，回调函数将获取所有已解析的IPv4和IPv6地址，就像DNS解析器返回的顺序一样。如果设置为`false`，IPv4地址将排在IPv6地址之前。默认值目前是`false`，但预计在不久的将来会变为`true`。

## 返回值

该方法返回错误、IP地址族和IP地址。

下面的例子说明了在Node.js中使用`dnsPromises.lookup()`方法：

## 示例

### 示例 1

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup() method
const options = {

// Setting family as 6 i.e. IPv6
    family: 6,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

// Calling dnsPromises.lookup() for hostname
// geeksforgeeks.org
dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
  console.log(' family: IPv%s address: %j', response.family, response.address);
});
```

**输出：**

```js
 family: IPv6 address: "fd00:0:14:13::22da:3e74"

```

### 示例 2

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup()
// method, all as true
const options = {
    all:true,
};

dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
    console.log('addresses: %j', response);
});
```

**输出：**

```js
addresses: [{"address":"34.218.62.116", "family":4},
{"address":"fd00:0:14:13::22da:3e74", "family":6}]

```

### 示例 3

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup()
//  method, all as true
const options = {
    all:true,
};

// Asynchronous function 
(async function() {

// Address from lookup function
    const addresses = await dnsPromises.lookup(
                    'geeksforgeeks.org', options);

// Printing  addresses
    console.log("from async: ");
    console.log(addresses);   
})();
```

**输出：**

```js
from async:
[ { address: '34.218.62.116', family: 4 },
  { address: 'fd00:0:14:13::22da:3e74', family: 6 } ]

```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/api/dns.html#dns_dnspromises_lookup_hostname_options](https://nodejs.org/api/dns.html#dns_dnspromises_lookup_hostname_options)