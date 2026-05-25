# Node.js http.ServerResponse.statusMessage 属性

> 原文: [https://www.geeksforgeeks.org/node-js-http-serverresponse-statusmessage-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-statusmessage-property/)

`http.ServerResponse.statusMessage` 是 [`http`](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 `ServerResponse` 的内置应用程序编程接口，用于控制当标头被刷新时将发送给客户端的状态消息。

**语法:**
```js
response.statusMessage
```

**参数**: 此方法不接受任何参数作为参数。

**返回值**: 该方法返回将要发送给客户端的状态消息。

### 示例 1: 文件名: `index.js`

## JavaScript
```js
// Node.js program to demonstrate the
// response.statusMessage APi

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(function(request, response){

  response.writeHead(200, {
    'Content-Length': Buffer.byteLength("GeeksforGeeks"),
    'Content-Type': 'text/plain'
  })

  // Getting the statusMessage
  // by using statusMessage API
  const value = response.statusMessage;

  // Display result
  // by using end() api
  response.end( "hello World", 'utf8', () => {
    console.log("displaying the result...");

    httpServer.close(()=>{
      console.log("server is closed")
    })
  });

  console.log("status message : " + value)
});

// Listening to http Server
httpServer.listen(PORT, () => {
  console.log("Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件:
```js
node index.js
```

**控制台输出:**
```js
Server is running at port 3000...
status message : OK
displaying the result...
server is closed
```

### 示例 2: 文件名: `index.js`

## JavaScript
```js
// Node.js program to demonstrate the
// response.statusMessage APi

// Importing http module
var http = require('http');

// Request and response handler
const http2Handlers = (request, response) => {

  response.writeHead(200, {
    'Content-Type': 'text/plain'
  }).end( "hello World", 'utf8', () => {
    console.log("displaying the result...");
  });

  // Getting the statusMessage
  // by using statusMessage API
  const value = response.statusMessage;

  httpServer.close(()=>{
    console.log("server is closed")
  })

  console.log("status message : " + value)
};

// Creating http Server
var httpServer = http.createServer(
  http2Handlers).listen(3000, () => {
  console.log("Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件:
```js
node index.js
```

**控制台输出:**
```js
Server is running at port 3000...
status message : OK
displaying the result...
server is closed
```

**浏览器输出:**
```js
hello world
```

**参考**: [https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_statusmessage](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_statusmessage)