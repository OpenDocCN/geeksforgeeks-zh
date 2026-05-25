# Node.js `response.writeHead()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-response-writehead-method/](https://www.geeksforgeeks.org/node-js-response-writehead-method/)

`response.writeHead()`（在 v0.1.0 中添加）是 `http` 模块的内置方法，用于向请求发送响应头。状态码是一个 3 位的 HTTP 状态码，例如 404。最后一个参数 `headers` 是响应头。可选地，可以给出人类可读的状态消息作为第二个参数。

当已经用 `response.setHeader()` 设置了头时，它们将与传递给 `response.writeHead()` 的任何头合并，优先使用传递给 `response.writeHead()` 的头。如果调用了这个方法，而 `response.setHeader()` 还没有被调用，那么它会直接把提供的头值写到网络通道上，而不在内部缓存，之后调用 `response.getHeaders()` 不会产生预期的结果。如果期望标题的渐进填充，并可能在将来进行检索和修改，请改用 `response.setHeader()`。

为了得到响应和恰当的结果，我们需要导入 `http` 模块。

## 语法

```js
response.writeHead(statusCode[, statusMessage][, headers]);
```

## 参数

它接受上面提到的和下面描述的三个参数：

*   **statusCode** < `number` >：它接受数字类型的状态码。
*   **statusMessage** < `string` >：它接受任何显示状态消息的字符串。
*   **headers** < `Object` >：它接受任何函数、数组或字符串。

## 返回值

< `http.ServerResponse` >：它返回对 `ServerResponse` 的引用，以便调用可以被链式调用。

下面的例子说明了 Node.js 中 `response.writeHead()` 方法的使用。

## 示例 1

**文件名: index.js**

```js
// Node.js program to demonstrate the
// response.writeHead() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
        function(request, response){

const body = 'hello world';

// Calling response.writeHead method
  response.writeHead(200, {
    'Content-Length': Buffer.byteLength(body),
    'Content-Type': 'text/plain'
  });

response.end(body);
});

// Listening to http Server
httpServer.listen(PORT, () => {
   console.log("Server is running at port 3000...");
});
```

**输出:**

> **输出:** 控制台内
>
> Server is running at port 3000...

现在在浏览器中运行 `http://localhost:3000/`。

> **输出:** 浏览器内
>
> hello world

## 示例 2

**文件名: index.js**

```js
// Node.js program to demonstrate the
// response.writeHead() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
        function(request, response){

// Setting up Headers
  response.setHeader('Content-Type', 'text/html');
  response.setHeader('Set-Cookie', ['type=ninja',
  'language=javascript']);
  response.setHeader('X-Foo', 'bar');

// Calling response.writeHead method
  response.writeHead(200,
     { 'Content-Type': 'text/plain' });

// Getting the set Headers
  const headers = response.getHeaders();

// Printing those headers
  console.log(headers);

// Prints Output on the
  // browser in response
  response.end('ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
   console.log(
"Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

> **输出:** 控制台内
>
> Server is running at port 3000...
>
> { 'content-type': 'text/plain',
>   'set-cookie': [ 'type=ninja', 'language=javascript' ],
>   'x-foo': 'bar' }

现在在浏览器中运行 `http://localhost:3000/`。

> **输出:** 浏览器内
>
> ok

`Content-Length` 以字节而不是字符给出。使用 `Buffer.byteLength()` 确定正文的长度（以字节为单位）。Node.js 不检查 `Content-Length` 和已经传输的正文长度是否相等。试图设置包含无效字符的标题字段名称或值将导致引发 `TypeError`。

## 参考

[https://nodejs.org/api/http.html#http_response_writehead_statuscode_statusmessage_headers](https://nodejs.org/api/http.html#http_response_writehead_statuscode_statusmessage_headers)