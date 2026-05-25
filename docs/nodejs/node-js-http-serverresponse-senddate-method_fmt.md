# Node.js http.ServerResponse.sendDate() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-http-serverresponse-senddate-method/](https://www.geeksforgeeks.org/node-js-http-serverresponse-senddate-method/)

`http.ServerResponse.sendDate` 是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 `ServerResponse` 的内置 API，用于检查日期头是否已经发送。HTTP 头也用于传递附加信息，如日期等。参考[这篇文章](https://www.geeksforgeeks.org/http-headers-date/)。

## 语法

```js
response.sendDate
```

## 参数

此方法不接受任何参数。

## 返回值

当且仅当日期头已经发送时，该方法返回 `true`。

## 示例 1：文件名：index.js

### JavaScript

```js
// Node.js program to demonstrate the
// response.sendDate() API

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
  function(request, response){

    // Checking if date header has been
    // sent or not by using sendDate API
    const value = response.sendDate;

    // Display result
    // by using end() api
    response.end( "Date header status: "
      + value, 'utf8', () => {
        console.log("displaying the result...");

        // Closing the server
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

### 执行命令

```js
node index.js
```

### 控制台输出

```js
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

### 浏览器输出

在浏览器的地址栏中粘贴本地主机地址 `http://localhost:3000/`。

```js
Date header status: true
```

## 示例 2：文件名：index.js

### JavaScript

```js
// Node.js program to demonstrate the
// response.sendDate() API

// Importing http module
var http = require('http');

// Request and response handler
const http2Handlers = (request, response) => {

  // Checking if date header has been
  // sent or not by using sendDate API
  const value = response.sendDate;

  // Display result by using end() api
  response.end( "Date header status: "
    + value, 'utf8', () => {
      console.log("displaying the result...");

      // Closing the server
      httpServer.close(()=>{
        console.log("server is closed")
      })
  });
};

// Creating http Server and listening
// on the port 3000
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => {
    console.log("Server is running at port 3000...");
});
```

### 执行命令

```js
node index.js
```

### 控制台输出

```js
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

### 浏览器输出

在浏览器的地址栏中粘贴本地主机地址 `http://localhost:3000/`。

```js
Date header status: true
```

## 参考

[https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_senddate](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_senddate)