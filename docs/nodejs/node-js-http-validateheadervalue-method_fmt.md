# Node.js http.validateHeaderValue() 方法

> 原文: [https://www.geeksforgeeks.org/node-js-http-validateheadervalue-method/](https://www.geeksforgeeks.org/node-js-http-validateheadervalue-method/)

`http.validateHeaderValue()`（在 v14.3.0 中添加）是 `http` 模块的一个内置属性，该模块在调用 `res.setHeader(name, value)` 时对提供的值执行低级验证。

将非法值作为 `value` 传递将导致引发 `TypeError`。未定义的值错误由代码标识：`ERR_HTTP_INVALID_HEADER_VALUE`。无效值字符错误由代码标识：`ERR_INVALID_CHAR`。

在向 HTTP 请求或响应传递标头之前，没有必要使用此方法。HTTP 模块将自动验证这样的头。

**注意：** 使用最新版本的 Node.js 获取需要的输出。

为了得到响应和恰当的结果，我们需要导入 `http` 模块。

```js
const http = require('http');
```

## 语法

```js
http.validateHeaderValue(name, value);
```

## 参数

该方法接受两个参数，如下所述：

*   `name` <`string`>：接受表头名称，不区分大小写。
*   `value` <`any`>：它接受任意函数、数组或字符串。

## 返回值

它不返回任何值，而是对提供的值执行低级验证。

下面的例子说明了在 Node.js 中 `http.validateHeaderValue()` 属性的使用。

### 示例 1

**文件名：** `index.js`

```js
// Node.js program to demonstrate the
// http.validateHeaderValue() Method

// Importing http module
const http = require('http');
const { validateHeaderValue } = require('http');

// Handling Errors via try-catch
try {
  validateHeaderValue('x-my-header', undefined);
} catch (err) {
  err instanceof TypeError; // true

  // Printing Errors
  console.log("Is undefined Invalid:",
    err.code === 'ERR_HTTP_INVALID_HEADER_VALUE'); // true

  // 'Invalid value "undefined" for header "x-my-header"'
  console.log(err.message);
}

// Handling Errors via try-catch
try {
  http.validateHeaderValue('x-my-header', 'oʊmɪɡə');
} catch (err) {
  err instanceof TypeError; // --> true

  // Printing Errors
  console.log("Is undefined Invalid:",
    err.code === 'ERR_INVALID_CHAR'); // true

  // 'Invalid character in header content ["x-my-header"]'
  console.log(err.message);
}
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

> Is undefined Invalid: true
> Invalid value "undefined" for header "x-my-header"
> Is undefined Invalid: true
> Invalid character in header content ["x-my-header"]

### 示例 2

**文件名：** `index.js`

```js
// Node.js program to demonstrate the
// http.validateHeaderValue() Method

// Importing http module
var http = require('http');

// Another way to import
const { validateHeaderValue } = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
  function(request, response) {

    // Setting up Headers
    response.setHeader('Content-Type', 'text/html');
    response.setHeader('Set-Cookie', ['type=ninja', 'language=javascript']);

    // Handling Errors via try-catch
    try {
      validateHeaderValue('Content-Type', 'text/html');
    } catch (err) {
      // false
      console.log("Error: ", err instanceof TypeError);
      // Printing Errors
      console.log(err.message);
    }

    try {
      http.validateHeaderValue('Set-Cookie', ['type=ninja', 'language=javascript']);
    } catch (err) {
      // false
      console.log("Error: ", err instanceof TypeError);
      // Printing Errors
      console.log(err.message);
    }

    // Getting the set Headers
    const headers = response.getHeaders();

    // Printing those headers
    console.log(headers);

    // Prints Output on the browser in response
    response.end('ok');
  });

// Listening to http Server
httpServer.listen(PORT, () => {
  console.log("Server is running at port 3000...");
});
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

> Server is running at port 3000...
> Error:  false
> Valid header...
> [Object: null prototype] {
  'content-type': 'text/html',
  'set-cookie': [ 'type=ninja', 'language=javascript' ]
}

现在在浏览器中运行 `http://localhost:3000/`。

**浏览器内输出：**

> ok

**参考：** [https://nodejs.org/api/http.html#http_http_validateheadervalue_name_value](https://nodejs.org/api/http.html#http_http_validateheadervalue_name_value)