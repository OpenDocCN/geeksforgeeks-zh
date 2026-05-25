# node.js dnsPromises.resolveTxt()方法

> 原文：[https://www.geeksforgeeks.org/node-js-dnspromises-resolvetxt-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolvetxt-method/)

该方法是`dns`模块的`Promises`对象中的内置API，用于使用DNS协议解析指定主机名的TXT（文本）查询记录。

## 语法

```js
dnsPromises.resolveTxt( hostname )
```

## 参数

该方法有一个参数，描述如下：

*   `hostname`：此参数指定一个字符串，表示要解析的主机名。

## 返回值

这个方法返回错误或地址。

## 例子

下面的例子说明了`dnsPromises.resolveTxt()`方法在Node.js中的使用：

### 例 1

```js
// Node.js program to demonstrate the
// dnsPromises.resolveTxt() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveTxt() method
dnsPromises.resolveTxt('google.com').then((res) => {
    console.log("for google : ");
    console.log(res);
});
```

**输出：**

```js
for google :
[ [ 'docusign=1b0a6754-49b1-4db5-8540-d2c12664b289' ],
  [ 'docusign=05958488-4752-4ef2-95eb-aa7ba8a3bd0e' ],
  [ 'facebook-domain-verification=22rm551cu4k0ab0bxsw536tlds4h95' ],
  [ 'globalsign-smime-dv=CDYX+XFHUw2wml6/Gb8+59BsH31KzUr6c1l2BPvqKX8=' ],
  [ 'v=spf1 include:_spf.google.com ~all' ]
]
```

### 例 2

```js
// Node.js program to demonstrate the
// dnsPromises.resolveTxt() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveTxt() method
// asynchronously
(async function() {

// Records from resolveTxt function
    const records = await dnsPromises.resolveTxt(
                    'geeksforgeeks.org');

// Printing  records
    console.log("from async: ");
    console.log(records);
})();
```

**输出：**

```js
from async:
[ [ 'v=spf1 include:amazonses.com include:_spf.google.com -all' ],
  [ 'fob1m1abcdp777bf2ncvnjm08n' ]
]
```

**注意：** 以上程序使用`node index.js`命令编译运行。

**参考：** [https://nodejs.org/api/dns.html#dns_dnspromises_resolvetxt_hostname](https://nodejs.org/api/dns.html#dns_dnspromises_resolvetxt_hostname)