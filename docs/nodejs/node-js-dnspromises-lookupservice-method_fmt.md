# Node.js dnsPromises.lookupService()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dnspromises-lookupservice-method/](https://www.geeksforgeeks.org/node-js-dnspromises-lookupservice-method/)

`dnsPromises.lookupService()`方法是`dns`模块`Promises`对象的内置应用程序编程接口，用于使用操作系统的底层`getnameinfo`实现将地址和端口号解析为主机名和服务。

## 语法:
```js
dnsPromises.lookupService( address, port )
```

## 参数:
该方法有两个参数，如上所述，如下所述:
*   `address`: 它指定一个表示要解析的地址的字符串。
*   `port`: 它是一个数字，指定要解析服务的地址的端口号。

## 返回值:
此方法返回错误、主机名和服务。

下面的例子说明了在Node.js中使用该方法:

## 例1:
```js
// Node.js program to demonstrate the
// dnsPromises.lookupService() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.lookupService() method
// for 127.0.0.1 port number 22
dnsPromises.lookupService('127.0.0.1', 22).then((res) => {
    console.log(res.hostname, res.service);
});
```

输出: 这里我电脑的名字是`my-lappy`
```js
my-lappy ssh
```

## 例2:
```js
// Node.js program to demonstrate the
// dnsPromises.lookupService() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup() method
const options = {
    // Setting family as 4 i.e. IPv4
    family: 4,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
    if(response){
        console.log(response);

        // Calling dnsPromises.lookupService() method
        dnsPromises.lookupService(response.address, 80).then((res) => {
            console.log(res.hostname, res.service);
        });
    }
});
```

输出:
```js
{ address: '34.218.62.116', family: 4 }
ec2-34-218-62-116.us-west-2.compute.amazonaws.com 334
```

注意: 以上程序使用`node index.js`命令编译运行。

参考: [https://nodejs.org/api/dns.html#dns_dnspromises_lookupservice_address_port](https://nodejs.org/api/dns.html#dns_dnspromises_lookupservice_address_port)