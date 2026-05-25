# Node.js `socket.connect()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-socket-connect-method/](https://www.geeksforgeeks.org/node-js-socket-connect-method/)

`socket.connect()`方法是`dgram`模块中`socket`类的内置应用程序编程接口，用于将特定的服务器连接到特定的端口和地址。

**语法：**

```js
const socket.connect(port[, address][, callback])
```

**参数：** 此方法接受以下参数：

*   `Port`：此参数保存端口号。
*   `Address`：此参数存储服务器地址信息。
*   `Callback`：此参数保存用于后续操作的回调函数。

**返回值：** 此方法不返回值。

## 示例 1

### 文件名：`index.js`

```js
// Node.js program to demonstrate the
// server.connect() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

// Displaying the client message
    process.stdout.write("UDP String: " + msg + "\n");

// Exiting process
    process.exit();
})
    // Binding server with port
    .bind(1234, () => {

// Getting the address information
        // for the server by using
        // address method
        const address = server.address()

// Display the result
        console.log(address);

});

// Connecting the server with particular local host
// and address by using connect() method
server.connect(1234, "localhost", () => {
    console.log("connected")
})

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出：**

```js
{ address: '0.0.0.0', family: 'IPv4', port: 1234 }
connected
UDP String: Hello
```

## 示例 2

### 文件名：`index.js`

```js
// Node.js program to demonstrate the
// server.connect() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

// Displaying the client message
    process.stdout.write("UDP String: " + msg + "\n");

// Exiting process
    process.exit();

});

// Catching the listening event
server.on('listening', () => {

// Getting address information for the server
    const address = server.address();

// Display the result
    console.log(`server listening
        ${address.address}:${address.port}`);

});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

// Adding a multicast address for others to join
    server.addMembership('224.0.0.114');

});

// Connecting the server with particular local host
// and address by using connect() method
server.connect(1234, "localhost", () => {
    console.log("connected")
})

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出：**

```js
server listening 0.0.0.0:1234
connected
UDP String: Hello
```

使用以下命令运行`index.js`文件：

```bash
node index.js
```

**参考：** [https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_connect_port_address_callback](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_connect_port_address_callback)