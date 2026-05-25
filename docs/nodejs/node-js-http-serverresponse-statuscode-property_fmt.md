# Node.js http.ServerResponse.statusCode 属性

> 原文：[https://www.geeksforgeeks.org/node-js-http-serverresponse-statuscode-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-statuscode-property/)

`http.ServerResponse.statusCode` 是 HTTP 模块中 `ServerResponse` 类的一个内置应用程序编程接口，用于此属性控制当标头被刷新时将发送给客户端的状态代码。

**语法：**

```js
const response.statusCode
```

**参数：** 该属性不接受任何参数作为参数。

**返回值：** 该属性返回将发送给客户端的状态代码。

**示例 1：Filename-index.js**

## JavaScript

```js
// Node.js program to demonstrate the
// response.statusCode method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
    function (request, response) {

        // Getting the statusCode
        // by using statusCode method
        const value = response.statusCode;

        // Display result by using end() method
        response.end("statusCode : " + value, 'utf8', () => {
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
statusCode : 200
```

**示例 2：Filename-index.js**

## JavaScript

```js
// Node.js program to demonstrate the
// response.statusCode method

// Importing http module
var http = require('http');

// Request and response handler
const httpHandlers = (request, response) => {

    // Getting the statusCode
    // by using statusCode method
    const value = response.statusCode;

    // Display result by using end() method
    response.end("statusCode : " + value, 'utf8', () => {
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
statusCode : 200
```

**参考：** [https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_statuscode](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_statuscode)