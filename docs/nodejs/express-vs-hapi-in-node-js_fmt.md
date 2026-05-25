# Node.js Express vs Hapi

> 原文: [https://www.geeksforgeeks.org/express-vs-hapi-in-node-js/](https://www.geeksforgeeks.org/express-vs-hapi-in-node-js/)

## Express 模块

为了使用 `express` 模块，我们需要在 `cmd` 上安装 **NPM**（`Node Package Manager`）和以下模块。

```js
// Creates package.json file
>> npm init

// Installs express module
>> npm install express --save  // OR
>> npm i express -s 
```

### 导入 Express 模块

导入 `express` 模块，将返回的实例存储到变量中。

**语法:**

```js
var express = require("express");
```

### 创建服务器

上面的语法调用 `express()` 函数，并创建一个新的 `express` 应用程序，该应用程序存储在 `app` 变量中。

**语法:**

```js
const app = express();

// OR Importing and creating express application
var express = require("express")();  
```

### 发送和侦听响应

它与客户端和服务器通信请求和响应。它需要 `PORT`（端口号）和 `IP`（IP地址）进行通信。

```js
app.listen(PORT, IP, Callback);
```

**参数:** 该方法接受三个参数，如下所述：

*   **`port`**（端口号）: 端口是帮助与客户端和服务器通信的通信端点。
*   **`ip`**（IP地址）: IP 代表主机或设备的 IPv4 或 IPv6 地址。
*   **`callback`**（函数）: 它接受一个函数。

下面的例子说明了 Node.js 中的 `Express.js` 模块。

**示例 1:** **文件名:** `index.js`

```js
// Node.js program to create server 
// with help of Express module

// Importing express 
const express = require('express');

// Creating new express app 
const app = express();

// PORT configuration
const PORT = process.env.PORT || 2020;

// IP configuration
const IP = process.env.IP || 2021;

// Create a route for the app
app.get('/', (req, res) => {
  res.send('Hello Vikas_g from geeksforgeeks!');
});

// Create a route for the app
app.get('*', (req, res) => {
  res.send('OOPS!! The link is broken...');
});

// Server listening to requests
app.listen(PORT, IP, () => {
  console.log(`The Server is running
    at: http://localhost:${PORT}/`);
});
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> Server running at: http://localhost:2020

现在在网页浏览器中输入 `http://127.0.0.1:2020/` 或 `http://localhost:2020/` 查看输出。

## Hapi 模块

为了使用 `hapi` 模块，我们需要在 `cmd` 上安装 **NPM**（`Node Package Manager`）和以下模块。

```js
// Creates package.json file
>> npm init

//  Installs hapi module
>> npm install @hapi/hapi --save 
```

### 导入 Hapi 模块

导入 `@hapi/hapi` 模块，并将返回的实例存储到变量中。

**语法:**

```js
var Hapi = require("@hapi/hapi");
```

### 创建服务器

上面的语法导入了 `@hapi/hapi` 模块，现在它创建了一个服务器。它与客户端和服务器通信请求和响应。它需要 `port`（端口号）和 `host`（主机名字符串）进行通信。

**语法:**

```js
const server = Hapi.server({port: 2020, host: 'localhost'});
```

**参数:** 该方法接受两个主要参数，如下所述：

*   **`port`**（端口号）: 端口是帮助与客户端和服务器通信的通信端点。
*   **`host`**（主机名）: 接受 `localhost`/`127.0.0.1`、`geeksforgeeks.org` 等主机名。

下面的例子说明了 Node.js 中的 `Hapijs` 模块。

**示例 2:** **文件名:** `index.js`

```js
// Node.js program to create server
// using hapi module

// Importing hapi module
const Hapi = require('@hapi/hapi');

// Creating Server
const server = Hapi.server({
    port: 2020,
    host: 'localhost'
});

// Creating route
server.route({
     method: 'GET',
     path: '/',
     handler: (request, hnd) => {
         return 'Hello GeeksForGeeks!';
     }
});

const start = async () => {
  await server.start();
   console.log('Server running at', server.info.uri);
};

process.on('unhandledRejection', (err) => {
   console.log(err);
   process.exit(1);
});

start();
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> Server running at: http://localhost:2020

现在在网页浏览器中输入 `http://localhost:2020/` 查看输出。