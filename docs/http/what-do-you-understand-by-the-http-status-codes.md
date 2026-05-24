# 你对 HTTP 状态码的理解是什么？

> 原文:[https://www . geeksforgeeks . org/通过 http-status-codes 了解什么/](https://www.geeksforgeeks.org/what-do-you-understand-by-the-http-status-codes/)

超文本传输协议是应用层的一种协议。它有助于在网络浏览器和网络服务器之间建立通信。当客户端请求任何信息时，浏览器使用数字状态代码发送响应。这些状态代码是从 100 到 599 的 3 位数形式。然后，客户端相应地对响应采取行动。客户可能并不总是完全理解状态代码或响应，但是可以通过看到数字状态代码的最左边/第一个数字来理解响应的性质/类别。

HTTP 状态代码可以用它们的第一个数字分为五个标准类:

*   **1xx–** This represents a **information response,** that is, the request has been received and is being processed, so we should wait for the final response.
*   **2xx–** This means **successful response,** that is, request was successfully received, understood and accepted.
*   **3xx–** This means **redirect the response,** that is, some further actions need to be taken to complete the request.
*   **4xx–** This represents **client error,** that is, the request contains incorrect syntax or cannot be implemented.
*   **5xx–** This represents **server error,** that is, the server failed to meet an obviously valid request.

在定义类时，其他两位数字没有如此重要的作用。

**下面提到了每类状态代码的几个例子:**

*   **101-Handover protocol-** This means that the server has been asked to switch the protocol and the server has agreed to do so.
*   **102-Processing-** This means that the request may contain many sub-requests, such as file operations, which may take a long time to complete. This helps prevent the client from thinking that the request has timed out.
*   **200–OK–** This is the standard response to all successful HTTP requests.
*   **202-Accepted-** This means that the request has been accepted by the server and has not been completed.
*   **307-Temporary redirection-** This means that the current request being sent to the server should be repeated with another URL. Future requests will still be sent to the original URL.
*   [T0】 308-–permanent redirect– Unlike the previous one, the current and all future requests will be redirected to another given website.
*   **404-Not found-** This just means that the sent request has not been found, but it may be available in the future.
*   **424-Dependency of failure-** This means that the request failed because it depends on another request and the request also failed.
*   **500-Internal server error-** When something unexpected happens and the server does not know exactly what it is, a standard error message appears.
*   **504-Gateway timed out-** This means that the server did not receive the response in time.