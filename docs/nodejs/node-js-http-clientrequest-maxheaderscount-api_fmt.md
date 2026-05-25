# Node.js http.ClientRequest.maxHeadersCount API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-http-client request-maxheadersscount API/

**`http.ClientRequest.maxHeadersCount`** 是 `http` 模块内 `ClientRequest` 类的内置应用编程接口，用于获取最大响应头计数限制。

**语法：**

`const request.maxHeadersCount`

**参数：** 本 `API` 不接受任何参数作为参数。

**返回值：** 该方法返回最大响应头计数限制。

**例 1：**

## index.js

```js
// Node.js program to demonstrate the   
// request.maxHeadersCount APi

// Importing http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('okay');
});

// Now that server is running
server.listen(3000, '127.0.0.1', () => {

// make a request
  const options = {
    port: 3000,
    host: '127.0.0.1',
    headers: {
      'Connection': 'Upgrade',
      'Upgrade': 'websocket'
    }
  };

// getting clinet request
  const req = http.request(options);

`req.maxHeadersCount = 200`

// getting maxHeadersCount
  // by using maxHeadersCount api
  const v = `req.maxHeadersCount`;

// display the result
  console.log("maxHeadersCount :- " + v)

process.exit(0)
});
```

**输出：**

![](img/35a71b8eee24caba8b5d38ad755d1c73.png)

**参考：** [https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_maxheaderscount](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_maxheaderscount)