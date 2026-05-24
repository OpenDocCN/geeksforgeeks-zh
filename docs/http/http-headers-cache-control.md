# HTTP 头|缓存控制

> 原文:[https://www.geeksforgeeks.org/http-headers-cache-control/](https://www.geeksforgeeks.org/http-headers-cache-control/)

**缓存控制头**是一个通用头，它指定了服务器响应和客户端请求的缓存策略。基本上，它给出了关于特定资源的缓存方式、缓存资源的位置及其在过期前达到的最大寿命(即生存时间)的信息。

**语法:**

```html
Cache-Control: <directive> [, <directive>]*
```

**指令:**此标头接受 15 条指令所有以下描述的指令:

*   **Public:** This instruction indicates that the response can be stored in any cache without any restrictions. If the response is not cacheable, it can still be cached.
*   **private:** means that only the browser cache is qualified to store the response.
*   **No cache:** indicates that the response can be stored in any cache without any restrictions even if it is not cacheable. The condition to be met here is that the stored response must be verified by the source server before being used.
*   **No storage:** indicates that the response cannot be stored in any cache.
*   **Maximum time = < seconds >:** It indicates the longest time that resources can be kept fresh and can be requested to access.
*   **s-maxage = < seconds >:** This instruction is mainly used for the shared cache of cdn. It overrides the longest-term instruction and expires when the header exists.
*   **Maximum outdated [= < seconds [T3】: 【T1] means that the client only accepts outdated responses. The optional time in seconds indicates the maximum acceptable obsolescence limit for the client.**
*   **min-fresh = < seconds >:** means that the client only accepts fresh responses within the specified duration specified in seconds.
*   **outdated-simultaneous-revalidation = < seconds >:** means that the outdated response will be accepted by the client, and the new response will be searched asynchronously. The time in seconds indicates the duration that the client will accept stale responses.
*   **Obsolete If the error = < seconds >:** means that the client will accept the obsolete response if it fails to check the new response. The time in seconds indicates the duration that the client accepts stale responses after the initial expiration.
*   **Must be re-verified:** It means that after caches become obsolete, they cannot use their obsolete resources without verification from the source server.
*   **Agent-re-authentication:** This instruction is similar to must-re-authentication. However, it is only applicable to shared cache, but ignored by private cache.
*   **Invariable:** means that the reactant remains unchanged for a period of time.
*   **No conversion:** indicates that the resource cannot be converted or modified into another form.
*   **Only cache:** indicates that the response of the client cannot use the network. This means that the cache can use the stored response or 504 status code.

**示例:**

*   To prevent caching, the following response headers can be used:

    ```html
    Cache-Control: no-store
    ```

*   To cache static assets, the following response headers can be used:

    ```html
    Cache-Control: public, max-age=604800, immutable
    ```

*   To re-verify, the following response headers can be used:

    ```html
    Cache-Control: no-cache
    Cache-Control: no-cache, max-age=0
    Cache-Control: no-cache, max-age=0, stale-while-revalidate=300
    ```

**支持的浏览器:**浏览器兼容 **HTTP Cache-Control 头**列表如下: