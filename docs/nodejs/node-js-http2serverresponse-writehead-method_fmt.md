# Node.js HTTP2 Server Response.writeHead()方法

> 原文：[https://www.geeksforgeeks.org/node-js-http2serverresponse-writehead-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-writehead-method/)

`Http2ServerResponse.writeHead()`是`http2`模块内的类`Http2ServerResponse`的内置应用程序编程接口，用于向请求发送响应头。

## 语法：
```js
response.writeHead(statusCode[, statusMessage][, headers])
```

## 参数：
该方法接受以下参数作为参数。

*   `statusCode`：是一个三位数的HTTP状态码。
*   `statusMessage`：是一个人类可读的状态消息。这是一个可选参数。
*   `headers`：这是作为参数传递的响应头。这是一个可选参数。

## 返回值：
这个方法没有什么可返回的。

## 如何生成私钥和公钥证书？

### 1. 文件名：私钥
打开记事本，复制粘贴以下密钥，将文件保存为`private-key.pem`。

### 2. 文件名：公共证书
打开记事本，复制粘贴以下密钥，将文件保存为`public-cert.pem`。

## 示例 1：Filename: index.js

### Javascript
```js
// Node.js program to demonstrate the
// Http2ServerResponse.writeHead() method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

// Sending the data to the client
    // by using response.writeHead() method
    response.writeHead(200, {
        'Content-Length': Buffer.byteLength('hello world'),
        'Content-Type': 'text/plain; charset=utf-8'
    });

// Sending the signal to the client
    response.end("hello world")
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestheader) => {
    stream.write('hello ');

// Getting all information of this http2stream object
    // by using state method
    const status = stream.state;

stream.end("priority weight : " + status.weight);

// Stopping the server
    // by using the close() method
    server.close(() => {
        console.log("server destroyed");
    })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({ 
    ':method': 'GET', ':path': '/' });

req.on('response', (responsesocket) => {
    console.log(responsesocket);
});

req.on('data', (data) => {
    console.log('Received: %s ',
    data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () => {
    client.close(() => {
        console.log("client destroyed");
    })
});
```

使用以下命令运行`index.js`文件：
```js
node index.js
```

## 输出：
```js
[Object: null prototype] {
  ':status': 200,
  'content-length': '11',
  'content-type': 'text/plain; charset=utf-8',
  date: 'Sun, 06 Dec 2020 14:12:00 GMT'
}
Received: hello world
client destroyed
server destroyed
```

## 示例 2：Filename: index.js

### Javascript
```js
// Node.js program to demonstrate the
// Http2ServerResponse.writeHead() method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

// Sending the data to the client
    // by using response.writeHead() method
    response.writeHead(200, {
        'Content-Length': Buffer.byteLength('hello world'),
        'Content-Type': 'text/plain; charset=utf-8'
    });

// Sending the signal to client
    response.end("hello world")
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(
    options, http2Handlers);

server.on('stream', (stream, requestheader) => {

// Stopping the server
    // by using the close() method
    server.close(() => {
        console.log("server destroyed");
    })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request({ 
    ':method': 'GET', ':path': '/' });

req.on('response', (responsesocket) => {
    console.log(responsesocket);
});

req.on('end', () => {
    client.close(() => {
        console.log("client destroyed");
    })
});
```

使用以下命令运行`index.js`文件：
```js
node index.js
```

## 输出：
```js
[Object: null prototype] {
  ':status': 200,
  'content-length': '11',
  'content-type': 'text/plain; charset=utf-8',
  date: 'Sun, 06 Dec 2020 14:39:31 GMT'       
}
```

## 参考：
[https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_writehead_statuscode_statusmessage_headers](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_writehead_statuscode_statusmessage_headers)