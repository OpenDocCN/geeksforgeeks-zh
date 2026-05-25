# Node.js os.networkInterfaces()方法

> 原文：[https://www.geeksforgeeks.org/node-js-os-networkinterfaces-method/](https://www.geeksforgeeks.org/node-js-os-networkinterfaces-method/)

`os.networkInterfaces()`方法是`os`模块内置的应用编程接口，用于获取计算机网络接口的信息。

**语法：**

```js
os.networkInterfaces()
```

**参数：** 此方法不接受任何参数。

**返回值：** 这个方法返回一个包含每个网络接口信息的对象。返回的对象将包含网络接口数组，该数组同样由以下属性组成：

*   `Address`：一个字符串，指定分配的网络地址，即 IPv4 或 IPv6。
*   `Netmask`：一个字符串，指定 IPv4 或 IPv6 子网掩码。
*   `Family`：一个字符串，指定系列，其值为 IPv4 或 IPv6。
*   `mac`：一个字符串，指定网络接口的 MAC 地址。
*   `Internal`：一个布尔值，如果接口是环回接口则为`true`，否则为`false`。
*   `Scope id`：指定 IPv6 范围 ID 的数字。
*   `cidr`：一个字符串，指定带有 CIDR 符号路由前缀的已分配 IPv4 或 IPv6 地址。如果子网掩码无效，则设置为`null`。

下面的例子说明了在 Node.js 中`os.networkInterfaces()`方法的使用：

**例 1：**

```js
// Node.js program to demonstrate the
// os.networkInterfaces() Method

// Allocating os module
const os = require('os');

// Print os.networkInterfaces() value
console.log(os.networkInterfaces());
```

**输出：**

```js
{ 'Wi-Fi':
   [ { address: 'fe80::242a:3451:7fb2:3ab1',
       netmask: 'ffff:ffff:ffff:ffff::',
       family: 'IPv6',
       mac: 'b3:52:16:13:de:b9',
       scopeid: 3,
       internal: false,
       cidr: 'fe80::242a:3451:7fb2:3ab1/64' },
     { address: '192.168.0.5',
       netmask: '255.255.255.0',
       family: 'IPv4',
       mac: 'b3:52:16:13:de:b9',
       internal: false,
       cidr: '192.168.0.5/24' } ],
  'Loopback Pseudo-Interface 1':
   [ { address: '::1',
       netmask: 'ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff',
       family: 'IPv6',
       mac: '00:00:00:00:00:00',
       scopeid: 0,
       internal: true,
       cidr: '::1/128' },
     { address: '127.0.0.1',
       netmask: '255.0.0.0',
       family: 'IPv4',
       mac: '00:00:00:00:00:00',
       internal: true,
       cidr: '127.0.0.1/8' } ] }
```

**例 2：**

```js
// Node.js program to demonstrate the
// os.networkInterfaces() Method

// Allocating os module
const os = require('os');

// Print os.networkInterfaces() value
var net_int = os.networkInterfaces();

var no_of_network_interfaces = 0;

for (var key in net_int) {
  console.log(key);
  var net_infos=net_int[key];

net_infos.forEach(element => {
  no_of_network_interfaces++;
  console.log("\tinterface:");

for (var attr in element){
      console.log("\t\t" + attr +
          " : " + element[attr] );
    }
  });
}

console.log("total number of Network "
  + "interfaces is " + no_of_network_interfaces);
```

**输出：**

```js
Wi-Fi
        interface:
                address : fe80::242a:3451:7fb2:3ab1
                netmask : ffff:ffff:ffff:ffff::
                family : IPv6
                mac : b3:52:16:13:de:b9
                scopeid : 3
                internal : false
                cidr : fe80::242a:3451:7fb2:3ab1/64
        interface:
                address : 192.168.0.5
                netmask : 255.255.255.0
                family : IPv4
                mac : b3:52:16:13:de:b9
                internal : false
                cidr : 192.168.0.5/24
Loopback Pseudo-Interface 1
        interface:
                address : ::1
                netmask : ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff
                family : IPv6
                mac : 00:00:00:00:00:00
                scopeid : 0
                internal : true
                cidr : ::1/128
        interface:
                address : 127.0.0.1
                netmask : 255.0.0.0
                family : IPv4
                mac : 00:00:00:00:00:00
                internal : true
                cidr : 127.0.0.1/8
total number of Network interfaces is 4
```

**注意：** 以上程序使用`node filename.js`命令编译运行。

**参考：** [https://nodejs.org/api/os.html#os_os_networkinterfaces](https://nodejs.org/api/os.html#os_os_networkinterfaces)