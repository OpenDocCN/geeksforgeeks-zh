# HTTP 状态代码|信息响应

> 原文:[https://www . geesforgeks . org/http-状态-代码-信息-响应/](https://www.geeksforgeeks.org/http-status-codes-informational-responses/)

HTTP 状态代码用于指示任何特定的 HTTP 请求是否已成功完成。HTTP 状态代码分为以下五个部分:

*   **信息响应(100–199)**
*   **成功响应(200–299)**
*   **重定向(300–399)**
*   **客户端错误(400–499)**
*   **服务器错误(500–599)**

有四个信息响应，分别是**继续**、**切换协议**、**处理**和**早期提示**。所有这些都描述如下:

*   **100 继续:**HTTP 100 继续信息响应状态代码用于通知客户端，到目前为止，请求一切正常。如果工作已经完成，那么客户端将忽略它，如果还没有完成，那么客户端将继续处理其他请求。请求完成后，服务器需要发送最终响应。
    当请求包含包含**100-继续**期望的期望报头字段时，100 响应表示服务器正在等待接收请求有效负载主体。客户端不需要发送带有**100-继续**期望的请求头。如果它不想发送请求正文。
    **状态:**

    ```html
    100 Continue
    ```

*   **101 Switching Protocols:** The HTTP 101 Switching Protocol Informational Response status code is used to indicate the protocols that are going to switch for the client request which includes the upgrade request header for the protocols. This status code can be used with the WebSockets.

    **状态:**

    ```html
    101 Switching Protocols
    ```

    **示例:**使用网络套接字执行。

    ```html
    HTTP/1.1 101 Switching Protocols
    Upgrade: websocket 
    Connection: Upgrade
    ```

*   **102 处理:**102 处理信息响应状态代码用于指示服务器收到了请求并正在处理该请求，但作为响应，到目前为止什么也没有。
*   **103 早期提示:**103 早期提示信息响应状态代码与链接头一起使用，以允许用户代理在服务器准备响应时重新加载资源。所以基本上，当服务器准备响应时，103 早期提示会强制重新加载资源，这样服务器就可以有很少的时间准备响应。
    **状态:**

    ```html
    103 Early Hints
    ```

**支持的浏览器:**与 **HTTP 状态代码信息响应**兼容的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧