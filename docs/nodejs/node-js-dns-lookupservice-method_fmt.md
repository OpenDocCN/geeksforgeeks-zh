# Node.js dns.lookupService()方法

> 原文: [https://www.geeksforgeeks.org/node-js-dns-lookupservice-method/](https://www.geeksforgeeks.org/node-js-dns-lookupservice-method/)

`dns.lookupService()`方法是`dns`模块的内置应用程序编程接口，用于使用操作系统的底层`getnameinfo`实现将地址和端口号解析为主机名。

## 语法

```js
dns.lookupService( address, port, callback )
```

## 参数

该方法有三个参数，如下所述：

*   `Address`: 指定一个字符串，表示要解析的地址。
*   `Port`: 一个数字，指定要解析服务的地址的端口号。
*   `Callback`: 指定地址和端口解析后要调用的函数。
    *   `Error`: 指定的生成错误。
    *   `Hostname`: 主机名的字符串表示。例如，`geeksforgeeks.org`。
    *   `Service`: 一个字符串，指定服务的名称。例如`http`。

## 返回值

该方法通过回调函数返回错误、主机名和服务。这些数据作为参数传递给回调函数。

下面的例子说明了在Node.js中`dns.lookupService()`方法的使用：

### 示例 1: 本地主机的IP

```js
// Accessing dns module
const dns = require('dns');

// Calling dns.lookupService() method for
// 127.0.0.1 port number 22
dns.lookupService('127.0.0.1', 22,
          (err, hostname, service) => {

// Printing hostname and service as callback
    console.log(hostname, service);
});
```

**输出:** 这里我电脑的名字是`my-lappy`

```js
my-lappy ssh
```

### 示例 2

```js
// Accessing dns module
const dns = require('dns');

// Setting options for dns.lookup() method
const options = {

// Setting family as 4 i.e. IPv4
    family: 4,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

dns.lookup('www.geeksforgeeks.org', 
        options, (err, address, family) => {

console.log('address:', address);
        if(err){
            console.log(err.stack);
        } else{

// Calling dns.lookupService() method 
        dns.lookupService(address, 80,
                 (err, hostname, service) => {
            if(err){
                console.log(err.stack);
            }

// Printing hostname and service
            // as callback
            console.log(hostname, service);
        });
    }
});
```

**输出:**

```js
address: 42.106.162.241
42-106-162-241.live.vodafone.in http
```

**注意:** 以上程序使用`node filename.js`命令编译运行。

**参考:** [https://nodejs.org/api/dns.html#dns_dns_lookupservice_address_port_callback](https://nodejs.org/api/dns.html#dns_dns_lookupservice_address_port_callback)