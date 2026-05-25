# Node.js `new Agent()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-new-agent-method/](https://www.geeksforgeeks.org/node-js-new-agent-method/)

Node.js `HTTP API` 是低级的，因此它可以支持 HTTP 应用程序。为了访问和使用 HTTP 服务器和客户端，我们需要调用它们（通过 `require('http')`）。HTTP 消息头表示为 JSON 格式。

`new Agent({})`（在 v0.3.4 中添加）方法是 `http` 模块的内置应用程序编程接口（API），其中默认的全局代理由 `http.request()` 使用，后者应该创建一个自定义的 `http.Agent` 实例。

## 语法

```js
new Agent({options})
```

## 参数

该函数接受如上所述的单个对象参数，如下所述：

### `options` <`Object`>

是可以在代理上设置的可配置选项。

*   `keepAlive` <`boolean`>：默认值设置为 `false`。无论是否有未完成的请求，它仍然保留套接字，因此它可以用于未来的请求，而无需重新建立连接（`TCP`）。使用代理时发送保活头连接，使用 `close` 连接关闭连接。
*   `keepAliveMsecs` <`number`>：默认值设置为 `false`。它表示 TCP 保持活动数据包的初始延迟，如果保持活动选项为 `false` 或未定义，将被忽略。
*   `maxSockets` <`number`>：默认值设置为 `Infinity`。它允许每个主机有最大数量的套接字，并且在达到最大数量之前，每个请求都使用一个新的套接字。
*   `maxTotalSockets` <`number`>：默认值设置为 `Infinity`。它允许所有主机的套接字总数达到最大值，在达到最大值之前，每个请求都使用一个新的套接字。
*   `maxFreeSockets` <`number`>：默认设置值为 `256`。为了在空闲状态下保持打开，它使用最大数量的插座，并且只有当 `keepAlive` 设置为 `true` 时才相关。
*   `scheduling` <`string`>：默认调度为 `fifo`。这是一种选择下一个空闲套接字进行调度和使用的策略。它有两种类型 `fifo` 或 `lifo`。`lifo`（`lifo`）选择最近使用的插座，而 `fifo`（`fifo`）选择最近最少使用的插座。
*   `timeout` <`number`>：它以 `毫秒` 为单位计算套接字超时，并在创建套接字时设置超时。

下面的例子说明了 Node.js 中 `new Agent({})` 方法的使用

## 示例 1

**文件名: `index.js`**

```js
// Node.js program to demonstrate the
// new agent({}) method

// Importing http module
const http = require('http');
var agent = new http.Agent({});

// Creating new agent
const aliveAgent = new http.Agent({ keepAlive: true,
maxSockets: 0, maxSockets: 5,  });

// Creating new agent
var agent = new http.Agent({});

// Creating new connection
var createConnection = aliveAgent.createConnection;

// Creating new connection
var createConnection = agent.createConnection;
console.log('Connection successfully created...');

// Printing the connection
console.log(createConnection);
console.log('Connection successfully created...');

// Printing the connection
console.log('Connection: ', createConnection);
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> 连接已成功创建…
>
> [Function: connection]
>
> 连接已成功创建…
>
> 连接: [Function: connection]

另一个模块 `agentkeepalive` 更适合与 Http 兼容，这使得处理请求更容易。为了使用 `agentkeepalive` 模块，我们需要安装 NPM（节点包管理器）和以下（在 `cmd` 上）。

```js
// Creates package.json file
>> npm init

// Installs express module
>> npm install agentkeepalive --save   OR
>> npm i agentkeepalive -s
```

**导入 `agentkeepalive` 模块:** 导入 `agentkeepalive` 模块，将返回的实例存储到变量中。

```js
const Agent = require('agentkeepalive');
```

## 示例 2

**文件名: `index.js`**

```js
// Node.js program to demonstrate the
// new agent({}) method

// Importing http module
const http = require('http');
// Importing agentkeepalive module
const Agent = require('agentkeepalive');
// Creating new agent
const keepAliveAgent = new Agent({});

// Options object
const options = {
  host: 'geeksforgeeks.org',
  port: 80,
  path: '/',
  method: 'GET',
  agent: keepAliveAgent,
};

// Requesting via http server module
const req = http.request(options, (res) => {
  // console.log(require('util').inspect(res, depth=0));
  // Printing statuscode
  console.log("StatusCode: ", res.statusCode);
  // Printing headers
  console.log("Headers: ", res.headers);
});

// Printing agent options
console.log("Agent Options: ", req.agent.options);
// console.log(req.agent.sockets);
req.end();
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> >> Agent Options: { keepAlive: true,
>
> freeSocketTimeout: 15000,
>
> timeout: 30000,
>
> socketActiveTtl: 0,
>
> path: null }
>
> >> StatusCode: 301
>
> >> Headers: { date: 'Wed, 19 Aug 2020 11:19:23 GMT',
>
> server: 'Apache',
>
> location: 'https://www.geeksforgeeks.org/',
>
> 'content-length': '238',
>
> 'keep-alive': 'timeout=5, max=100',
>
> connection: 'Keep-Alive',
>
> 'content-type': 'text/html; charset=iso-8859-1' }

**参考:** [https://nodejs.org/api/http.html#http_new_agent_options](https://nodejs.org/api/http.html#http_new_agent_options)