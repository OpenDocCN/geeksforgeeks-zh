# HTTP 头：Retry-After

> 原文：[https://www.geeksforgeeks.org/http-headers-retry-after/](https://www.geeksforgeeks.org/http-headers-retry-after/)

HTTP 头用于通过 HTTP 请求或响应传递附加信息。HTTP `Retry-After` 响应头是一个 HTTP 响应标头，它指示在发出另一个请求之前要等待多长时间。根据不同的状态代码，`Retry-After` 标头有不同的用例。

*   **status code 503:** 503 用于表示服务不可用。`Retry-After` 与 503 一起使用，告知用户服务预计何时恢复。它用于处理计划内的停机。
*   **status code 301:** 301 用于表示资源已永久移动。`Retry-After` 与 301 一起使用，告知用户在发出重定向请求前需要等待的最短时间。
*   **status code 429:** 429 用于表示请求过多。`Retry-After` 与 429 一起使用，告知用户在发出另一个请求前需要等待多长时间。

## 语法

```
Retry-After: <http-date>
Retry-After: <delay-seconds>
```

## 指令

该报头接受两个指令，如上所述，如下所述：

*   `http-date`：它指示应重新传输请求的日期。
*   `delay-seconds`：是一个整数值，表示用户应等待多少秒后重新发送请求。

## 示例

本示例将说明 HTTP `Retry-After` 头：

*   使用 `date` 指令，客户端可以在指定日期后的特定时间内重试请求。

```
Retry-After: Sun, 27 Oct 2019 09:45:00 GMT
```

*   使用 `delay-seconds` 指令，客户端在指定的秒数后可以重试请求。

```
Retry-After: 180
```

## 支持的浏览器

与 HTTP `Retry-After` 标题兼容的浏览器如下：