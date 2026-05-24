# HTTP 头|重试-在

之后

> 原文:[https://www.geeksforgeeks.org/http-headers-retry-after/](https://www.geeksforgeeks.org/http-headers-retry-after/)

HTTP 头用于通过 HTTP 请求或响应传递附加信息。HTTP **重试-在**之后标头是一个 HTTP 响应标头，它指示在发出另一个请求之前要等待多长时间。根据不同的状态代码，响应后重试标头有不同的用例。

*   **status code 503:** 503 is used to indicate that the service is unavailable. "After Retry" is used with 503, which tells the user when the service is expected to be unavailable. It is used to handle planned downtime.
*   **status code 301:** 301 is used to indicate that resources are permanently moved. Retry-After is used with 301, which tells the user the minimum time to wait before issuing a redirect request.
*   **status code 429:** 429 ID is used to indicate that there are too many requests. Retry-After is used with 429 to tell the user how long to wait before making another request.

**语法:**

```html
Retry-After: <http-date>
Retry-After: <delay-seconds>

```

**指令:**该报头接受两个指令，如上所述，如下所述:

*   **[http-date:** It indicates the date used when the request should be retransmitted.
*   **Delay-second:** is an integer value indicating how many seconds the user should resend the request.

**示例:**本示例将说明 HTTP Retry-After 头:

*   With the date instruction, the client can retry the request within a specified time after the date.

    ```html
    Retry-After: Sun, 27 Oct 2019 09:45:00 GMT
    ```

*   Use the delay-second instruction, after which the specified second client can retry the request.

    ```html
    Retry-After: 180
    ```

**支持的浏览器:**与 **HTTP 重试兼容的浏览器-在**之后标题如下: