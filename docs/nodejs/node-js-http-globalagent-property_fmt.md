# Node.js http.globalAgent 属性

> 原文: [https://www.geeksforgeeks.org/node-js-http-globalagent-property/](https://www.geeksforgeeks.org/node-js-http-globalagent-property/)

`http.globalAgent`（在 v0.5.9 中添加）属性是 `http` 模块的内置属性，用作所有 HTTP 客户端请求的默认值。它是代理的全局实例。

代理为给定的主机和端口维护一个挂起请求的队列，为每个请求重用一个套接字连接，直到队列为空，此时套接字要么被销毁，要么被放入池中，在池中它被保留以再次用于对同一主机和端口的请求。

为了得到响应和恰当的结果，我们需要导入 `http` 模块。

## 导入

```js
const http = require('http');
```

## 语法

```js
http.globalAgent
```

## 参数

该属性不接受任何参数。

## 返回值

返回类型为 `http.Agent`，负责管理 HTTP 客户端的连接持久性和重用。

下面的例子说明了 `http.globalAgent` 属性在 Node.js 中的使用。

## 示例 1

### 文件名: index.js

```js
// Node.js program to demonstrate the
// http.globalAgent Method

// Importing http module
var http = require('http');
const { globalAgent } = require('http');

const PORT = process.env.PORT || 3000;

console.log(globalAgent);

// Creating http Server
var httpServer = http.createServer(
    function(request, response) {

        console.log(globalAgent);

        var Output = "Hello Geeksforgeeks..., "
            + "Output of global agent is: " +
            JSON.stringify(globalAgent);

        // Prints Output on the browser in response
        response.write(Output);
        response.end('ok');
    });

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

### 输出

控制台中的输出:

```
Server is running at port 3000...
Agent {
  _events: [Object: null prototype] {
    free: [Function (anonymous)],
    newListener: [Function: maybeEnableKeylog]
  },
  _eventsCount: 2,
  _maxListeners: undefined,
  defaultPort: 80,
  protocol: 'http:',
  options: { path: null },
  requests: {},
  sockets: {},
  freeSockets: {},
  keepAliveMsecs: 1000,
  keepAlive: false,
  maxSockets: Infinity,
  maxFreeSockets: 256,
  scheduling: 'fifo',
  maxTotalSockets: Infinity,
  totalSocketCount: 0,
  [Symbol(kCapture)]: false
}
```

现在在浏览器中运行 `http://localhost:3000/`。

浏览器中的输出:

```
Hello Geeksforgeeks..., Output of global agent is: {"_events":{},"_eventsCount":2,"defaultPort":80,"protocol":"http:","options":{"path":null},"requests":{},"sockets":{},"freeSockets":{},"keepAliveMsecs":1000,"keepAlive":false,"maxSockets":null,"maxFreeSockets":256,"scheduling":"fifo","maxTotalSockets":null,"totalSocketCount":0}ok
```

## 参考

[https://nodejs.org/api/http.html#http_http_globalagent](https://nodejs.org/api/http.html#http_http_globalagent)