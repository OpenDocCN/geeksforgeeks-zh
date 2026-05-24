# 在 HTTP 中请求与请求 KoaJS

> 原文:[https://www . geesforgeks . org/requesting-in-http-vs-requesting-koajs/](https://www.geeksforgeeks.org/requesting-in-http-vs-requesting-koajs/)

**Node.js:** Node.js 是一个开源的跨平台运行时环境，用于在浏览器外执行 JavaScript 代码。你需要记住 NodeJS 不是一个框架，也不是一种编程语言。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。

**http 模块**

**导入** ***http*** **模块:**导入 *http* 模块，并将返回的 http 实例存储到变量中。

**语法:**

```html
var http = require("http");
```

**创建和绑定服务器:**使用 *createServer()* 方法创建一个服务器实例，并使用 listen()方法将其绑定到某个端口。

**语法:**

```html
const server = http.createServer().listen(port)
```

**参数:**此方法( *listen()* )接受如上所述的单个参数，如下所述:

*   **港口** < *号* > **:** 港口在包含注册港口和动态港口的 *1024* 至 *65535* 范围内。

下面的例子说明了 Node.js 中 *http* 模块的使用

**示例 1:文件名:index.js**

```html
// Node.js program to create  
// http server  

// Using require to access http module  
const http = require("http");

// Port number
const PORT = process.env.PORT || 2020;

// Creating server
const server = http.createServer(
  // Server listening on port 2020
  function (req, res) {
     // Write a response to the client
     res.write('Hello geeksforgeeks!');  
     res.end();   
  }
)
.listen(PORT, error => {
 // Prints in console
 console.log(`Server listening on port ${PORT}`)
 });
```

使用以下命令运行 **index.js** 文件:

```html
node index.js
```

**输出:**

> 服务器正在端口 2020 上侦听

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020* 查看输出。

**Koa 模块**

为了使用 Koa 模块，我们需要安装 NPM(节点包管理器)和以下模块(在 cmd 上)。

```html
>> npm init // Creates package.json file
>> npm install koa --save //  Installs express module
>> npm i koa -s // OR 

```

**导入 KoaJS 模块:**导入 *KoaJS* 模块，并将返回的实例存储到变量中。

**语法:**

```html
var koa = require("koa"); // Importing koa module
```

**创建服务器:**上面的语法导入 koa 模块，并创建一个新的 koa 应用程序，该应用程序存储在应用程序变量中。

**语法:**

```html
const app = new koa();  // Creating koa application
```

**发送和侦听响应:**它与客户端和服务器通信请求和响应。它需要 PORT < *号* >和 IP < *号* >进行通信。

```html
app.listen(PORT, IP, Callback);
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **端口** < *号码* > **:** 端口是帮助与客户端和服务器通信的通信端点。

*   **IP** < *编号*>**:**IP 代表主机或设备的 IPv4 或 IPv6 地址。

*   **回调** < *函数* > **:它接受一个函数。**

下面的例子说明了 Node.js 中的 *KoaJS* 模块

**示例 2:文件名:index.js**

```html
// Node.js program to create server  
// with help of Koa module

// Importing koa  
const koa = require('koa');

// Creating new koa app
const app = new koa();

// PORT configuration
const PORT = process.env.PORT || 2020;

// IP configuration
const IP = process.env.IP || 2021;

app.use(function *() {
 this.body = "Hello GeeksForGeeks!";
});

// Server listening to requests
app.listen(PORT, IP, ()=>{
console.log("Server started at port", PORT);
});
```

使用以下命令运行 **index.js** 文件:

```html
node index.js
```

**输出:**

> 服务器运行在端口 2020

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020/* 查看输出。