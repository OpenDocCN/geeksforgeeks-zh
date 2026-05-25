# node.js response.addTrailers()方法

> 原文: [https://www.geeksforgeeks.org/node-js-response-addtrailers-method/](https://www.geeksforgeeks.org/node-js-response-addtrailers-method/)

`response.addTrailers()` (在 v0.3.0 中添加)方法是 `http` 模块的内置应用程序编程接口，它将 http 尾部标头(一个标头，但在消息的末尾)添加到响应中。只有当响应使用分块编码时，才会发出预告片；如果不是(例如，如果请求是 HTTP/1.0)，它们将被无声地丢弃。HTTP 要求发送尾部头，以便发出尾部，在其值中包含一个头部字段列表。

当标题设置为 `response.setHeader()` 时，它们将与传递给 `response.writeHead()` 的任何标题合并，优先传递给 `response.writeHead()` 的标题。

为了得到响应和恰当的结果，我们需要导入 `http` 模块。

## 语法

```js
const http = require('http');
```

```js
response.addTrailers(headers);
```

## 参数

该属性接受如上所述的单个参数，如下所述:

*   `headers` <`string`>: 它接受 HTTP 尾随标头的名称(一个标头，但在消息的末尾)来响应。

## 返回值

不返回值，而是设置一个表头，如下所述。

下面的例子说明了在 Node.js 中 `response.addTrailers()` 属性的使用。

### 示例 1

**文件名: index.js**

```js
// Node.js program to demonstrate the
// response.addTrailers() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
       function(request, response) {

// Setting up Headers
  response.setHeader('Alfa', 'Beta');

response.writeHead(200, {
    'Content-Type': 'text/plain',
    'Trailer': 'Content-MD5'
  });
  response.addTrailers({'Content-MD5':
    '7895bf4b8828b55ceaf47747b4bca667'});

console.log(response.getHeaders());
  response.end('Trailer Added, ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log(
      "Server is running at port 3000...");
});
```

现在在浏览器中运行 `http://localhost:3000/`。

**输出: 在控制台**

> Server is running at port 3000...
> [Object: null prototype] {
>   Alfa: 'Beta',
>   'content-type': 'text/plain',
>   trailer: 'Content-MD5'
> }

**输出: 在浏览器中**

```js
Trailer Added, ok
```

### 示例 2

**文件名: index.js**

```js
// Node.js program to demonstrate the
// response.addTrailers() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
          function(req, response) {

// Setting up Headers
  response.setHeader('Alfa1', '');
  response.setHeader('Cookie-Setup',
       ['Alfa=Beta', 'Beta=Romeo']);

response.writeHead(200, {
    'Content-Type': 'text/plain',
    'Trailer': 'Content-MD5'
  });

// addTrailers Content-MD5
  response.addTrailers({'Content-MD5':
    '7895bf4b8828b55ceaf47747b4bca667'});

// Adding Cookie-Setup as trailer
  // ( Not gets added as trailer )
  response.addTrailers({ 'Cookie-Setup':
       ['Alfa=Beta', 'Beta=Romeo'] });

// Checking and printing the headers
  console.log("Calling trailer by getHeader :",
  response.getHeader('Content-MD5'));

// console.log("Calling trailer by getHeader :",
  response);

// Getting the set Headers
  const headers = response.getHeaders();

// Printing those headers
  // Header
  console.log("Printing _header: ", response._header);

// Trailer
  console.log("Printing _trailer: ", response._trailer);

// All headers
  console.log("Printing All headers: ", headers);

var Output = "Hello Geeksforgeeks..., "
    + "Available headers and trailers are:"
    + JSON.stringify(headers);

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

```js
node index.js
```

**输出:**

> 在控制台中
> Server is running at port 3000...
> Calling trailer by getHeader : undefined
> Printing _header: HTTP/1.1 200 OK
> Alfa1:
> cookie-setup: Alfa=Beta
> cookie-setup: Beta=Romeo
> content-type: text/plain
> trailer: Content-MD5
> Date: Wed, 09 Sep 2020 06:03:32 GMT
> Connection: keep-alive
> Transfer-Encoding: chunked
>
> Printing _trailer: Cookie-Setup: Alfa=Beta, Beta=Romeo
> Printing All headers: [Object: null prototype] {
>   alfa1: '',
>   'cookie-setup': [ 'Alfa=Beta', 'Beta=Romeo' ],
>   'content-type': 'text/plain',
>   trailer: 'Content-MD5'
> }

现在在浏览器中运行 `http://localhost:3000/`。

**输出: 在浏览器中**

> Hello Geeksforgeeks..., Available headers and trailers are:{"Alfa1":"","cookie-setup":["Alfa=Beta","Beta=Romeo"],"content-type":"text/plain","trailer":"Content-MD5"}ok

**参考:** [https://nodejs.org/api/http.html#http_response_addtrailers_headers](https://nodejs.org/api/http.html#http_response_addtrailers_headers)