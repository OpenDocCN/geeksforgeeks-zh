# Node.js HTTP 模块完整参考

> 原文: [https://www.geeksforgeeks.org/node-js-http-module-complete-reference/](https://www.geeksforgeeks.org/node-js-http-module-complete-reference/)

为了在 Node.js 中发出 HTTP 请求，Node.js 中有一个内置的模块 HTTP，用于通过 HTTP 传输数据。为了在节点中使用 HTTP 服务器，我们需要 HTTP 模块。HTTP 模块创建一个 HTTP 服务器，该服务器监听服务器端口并向客户端返回响应。

下面列出了 HTTP 模块的完整列表:

[Node.js HTTP 模块](https://www.geeksforgeeks.org/node-js-http-module/)

## 类: `http.Agent`

*   [Node.js `new Agent()` method](https://www.geeksforgeeks.org/node-js-new-agent-method/)
*   [Node.js `Agent.createConnection()` method](https://www.geeksforgeeks.org/node-js-agent-createconnection-method/)
*   [Node.js `Agent.maxSockets` method](https://www.geeksforgeeks.org/node-js-agent-maxsockets-method/)
*   [Node.js `Agent.maxFreeSockets`](https://www.geeksforgeeks.org/node-js-agent-maxfreesockets-method/)

## 类: `http.ClientRequest`

*   [Node.js `http.ClientRequest.abort()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-abort-method/)
*   [Node.js `http.ClientRequest.connection` property](https://www.geeksforgeeks.org/node-js-http-clientrequest-connection-property/)
*   [Node.js `http.ClientRequest.protocol` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-protocol-method/)
*   [Node.js `http.ClientRequest.aborted` property](https://www.geeksforgeeks.org/node-js-http-clientrequest-aborted-property/)
*   [Node.js `http.ClientRequest.path` property](https://www.geeksforgeeks.org/node-js-http-clientrequest-path-property/)
*   [Node.js `http.ClientRequest.setNoDelay()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-setnodelay-method/)
*   [Node.js `http.ClientRequest.setSocketKeepAlive()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-setsocketkeepalive-method/)
*   [Node.js `http.ClientRequest.removeHeader()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-removeheader-method/)
*   [Node.js `http.ClientRequest.reusedSocket` property](https://www.geeksforgeeks.org/node-js-http-clientrequest-reusedsocket-property/)
*   [Node.js `http.ClientRequest.setHeader()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-setheader-method/)
*   [Node.js `http.ClientRequest.setTimeout()` method](https://www.geeksforgeeks.org/node-js-http-clientrequest-settimeout-method/)
*   [Node.js `http.ClientRequest.socket` property](https://www.geeksforgeeks.org/node-js-http-clientrequest-socket-property/)

## 类: `http.Server`

*   [Node.js `http.Server.setTimeout()` method](https://www.geeksforgeeks.org/node-js-http-server-settimeout-method/)
*   [Node.js `http.Server.timeout` property](https://www.geeksforgeeks.org/node-js-http-server-timeout-property/)
*   [Node.js `http.Server.close()` method](https://www.geeksforgeeks.org/node-js-http-server-close-method/)
*   [Node.js `http.Server.headersTimeout` method](https://www.geeksforgeeks.org/node-js-http-server-headerstimeout-method/)
*   [Node.js `http.Server.maxHeadersCount` property](https://www.geeksforgeeks.org/node-js-http-server-maxheaderscount-property/)

## 类: `http.ServerResponse`

*   [Node.js `http.ServerResponse.writableFinished` property](https://www.geeksforgeeks.org/node-js-http-serverresponse-writablefinished-property/)
*   [Node.js `http.ServerResponse.writableEnded` property](https://www.geeksforgeeks.org/node-js-http-serverresponse-writableended-property/)
*   [Node.js `http.ServerResponse.statusCode` property](https://www.geeksforgeeks.org/node-js-http-serverresponse-statuscode-property/)
*   [Node.js `http.ServerResponse.headersSent` property](https://www.geeksforgeeks.org/node-js-http-serverresponse-headerssent-property/)
*   [Node.js `http.ServerResponse.setTimeout()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-settimeout-method/)
*   [Node.js `http.ServerResponse.socket` API](https://www.geeksforgeeks.org/node-js-http-serverresponse-socket-api/)
*   [Node.js `http.ServerResponse.statusMessage` property](https://www.geeksforgeeks.org/node-js-http-serverresponse-statusmessage-property/)
*   [Node.js `http.ServerResponse.writeProcessing()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-writeprocessing-method/)
*   [Node.js `http.ServerResponse.sendDate()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-senddate-method/)
*   [Node.js `http.ServerResponse.getHeader()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-getheader-method/)
*   [Node.js `http.ServerResponse.end()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-end-method/)
*   [Node.js `http.ServerResponse.connection()` method](https://www.geeksforgeeks.org/node-js-http-serverresponse-connection-method/)

## 类: `http.IncomingMessage`

*   [Node.js `http.IncomingMessage.url()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-url-method/)
*   [Node.js `http.IncomingMessage.trailers()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-trailers-method/)
*   [Node.js `http.IncomingMessage.statusMessage()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-statusmessage-method/)
*   [Node.js `http.IncomingMessage.method()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-method-method/)
*   [Node.js `http.IncomingMessage.rawHeaders()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-rawheaders-method/)
*   [Node.js `http.IncomingMessage.statusCode()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-statuscode-method/)
*   [Node.js `http.IncomingMessage.rawTrailers()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-rawtrailers-method/)
*   [Node.js `http.IncomingMessage.aborted()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-aborted-method/)
*   [Node.js `http.IncomingMessage.headers()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-headers-method/)
*   [Node.js `http.IncomingMessage.httpVersion()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-httpversion-method/)
*   [Node.js `http.IncomingMessage.complete()` method](https://www.geeksforgeeks.org/node-js-http-incomingmessage-complete-method/)