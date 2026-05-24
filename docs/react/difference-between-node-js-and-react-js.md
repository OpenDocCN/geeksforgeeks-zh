# node . js 和 React.js 的区别

> 原文:[https://www . geesforgeks . org/difference-node-js-and-react-js/](https://www.geeksforgeeks.org/difference-between-node-js-and-react-js/)

[**node . js:**](https://www.geeksforgeeks.org/nodejs-tutorials/)node . js 是一个开源和跨平台运行时环境，用于在浏览器外执行 [JavaScript](https://www.geeksforgeeks.org/JavaScript-tutorial/) 代码。你需要记住 **NodeJS 不是框架，也不是编程语言** 。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。

**Node.js 的特性:**我们还可以使用其他编程语言来构建后端服务，所以我将解释 node . js 的不同之处。

1.  The large-scale ecosystem is an open source library.
2.  Have asynchronous or non-blocking properties.

**代码:** 下面是一个如何包含HTTP 模块来构建服务器的例子。

**档案名称:app . js**

## 【JavaScript】

```jsx
var http = require('http');

// Create a server object:
http.createServer(function (req, res) {

    // Write a response to the client
    res.write('GeeksforGeeks');

    // End the response
    res.end();

// The server object listens on port 8080
}).listen(8080);
```