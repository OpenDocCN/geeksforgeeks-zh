# Node.js `http.ServerResponse.headersSent` 属性

> 原文：[https://www.geeksforgeeks.org/node-js-http-serverresponse-headerssent-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-headerssent-property/)

`http.ServerResponse.headersSent` 是 HTTP 模块内 `ServerResponse` 类的一个内置 API，用于检查响应头是否已经发送。

**语法：**
```js
const response.headersSent
```

**参数：** 该属性不接受任何参数。

**返回值：** 当且仅当响应头已经发送时，此属性返回 `true`，否则返回 `false`。

## 示例 1：Filename - index.js

### JavaScript

```js
// Node.js program to demonstrate the
// response.headersSent() method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
    function (request, response) {

        // Checking if response header is sent or not
        // by using headersSent method
        const value = response.headersSent;

        // Display result by using end() method
        response.end("Headers have been sent : "
            + value, 'utf8', () => {
                console.log("displaying the result...");

                httpServer.close(() => {
                    console.log("server is closed")
                })
            });
    });

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件：
```js
node index.js
```

**输出：**
```js
Server is running at port 3000...
displaying the result...
server is closed
```

现在打开浏览器，转到 `http://localhost:3000/`，会看到如下输出：
```js
Headers have been sent : false
```

## 示例 2：Filename - index.js

### JavaScript

```js
// Node.js program to demonstrate the
// response.headersSent() method

// Importing http module
var http = require('http');

// Request and response handler
const httpHandlers = (request, response) => {

    // Checking if response header is sent or not
    // by using headersSent method
    const value = response.headersSent;

    // Display result by using end() method
    response.end("Headers have been sent : "
        + value, 'utf8', () => {
            console.log("displaying the result...");

            httpServer.close(() => {
                console.log("server is closed")
            })
        });
};

// Creating http Server
var httpServer = http.createServer(
    httpHandlers).listen(3000, () => {
        console.log("Server is running at port 3000...");
    });
```

使用以下命令运行 `index.js` 文件：
```js
node index.js
```

**输出：**
```js
Server is running at port 3000...
displaying the result...
server is closed
```

现在打开浏览器，转到 `http://localhost:3000/`，会看到如下输出：
```js
Headers have been sent : false
```

**参考：** [https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_headerssent](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_headerssent)