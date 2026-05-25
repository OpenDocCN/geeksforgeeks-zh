# Node.js http.IncomingMessage.trailers() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-http-incomingmessage-trailers-method/](https://www.geeksforgeeks.org/node-js-http-incomingmessage-trailers-method/)

`http.IncomingMessage.trailers` 是 `http` 模块内 `IncomingMessage` 类的内置 API，用于获取请求/响应的 [trailer](https://www.geeksforgeeks.org/http-headers-trailer/) 对象。

**语法:**

```js
request.trailers 或 response.trailers
```

**参数:** 该方法不接受任何参数。

**返回值:** 该方法返回请求或响应的 trailer 对象。

## 示例 1: 文件名: index.js

```js
// Node.js program to demonstrate the
// request.trailers API

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
  function(request, response){

    // Getting trailers
    // by using request.trailers API
    const value = request.trailers;

    // Display the request trailers
    console.log(value)

    // Display the result
    response.end("hello world", 'utf8', () => {
      console.log("displaying the result...");

      //Closing the server
      httpServer.close(()=>{
        console.log("server is closed")
      })
    });
  });

// Listening to http Server
httpServer.listen(PORT, () => {
  console.log("Server is running at port 3000...");
});
```

**执行命令:**

```bash
node index.js
```

**控制台输出:**

```text
Server is running at port 3000...
{}
displaying the result...
{}
displaying the result...
server is closed
server is closed
```

**浏览器输出:** 在浏览器的地址栏中粘贴 localhost 地址 `http://localhost:3000/`。

## 示例 2: 文件名: index.js

```js
// Node.js program to demonstrate the
// request.trailers API

// Importing http module
var http = require('http');

// Request and response handler
const http2Handlers = (request, response) => {

  // Getting trailers
  // by using request.trailers API
  const value = request.trailers;

  // Display the request trailer
  console.log(value)

  // Display result
  response.end("GeeksForGeeks", 'utf8', () => {
    console.log("displaying the result...");

    //Closing the server
    httpServer.close(()=>{
      console.log("server is closed")
    })
  });
};

// Creating http Server and listening
// on the 3000 port
var httpServer = http.createServer(
  http2Handlers).listen(3000, () => {
  console.log("Server is running at port 3000...");
});
```

**执行命令:**

```bash
node index.js
```

**控制台输出:**

```text
Server is running at port 3000...
{}
displaying the result...
{}
displaying the result...
server is closed
server is closedserver is closed
```

**浏览器输出:** 在浏览器的地址栏中粘贴 localhost 地址 `http://localhost:3000/`。

```text
GeeksForGeeks
```

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_message_trailers](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_message_trailers)