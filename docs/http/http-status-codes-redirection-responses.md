# HTTP 状态代码|重定向响应

> 原文:[https://www . geesforgeks . org/http-状态-代码-重定向-响应/](https://www.geeksforgeeks.org/http-status-codes-redirection-responses/)

HTTP 状态代码是浏览器和站点服务器之间的对话。服务器以三位数代码的形式对浏览器的请求做出响应，称为 HTTP 状态代码。HTTP 状态代码分为以下五个部分。

*   信息回应(100–199)
*   成功响应(200–299)
*   重定向(300–399)
*   客户端错误(400–499)
*   服务器错误(500–599)

**重定向响应:**

*   **300 选择题:**是一个链接列表。该请求最多可以有五个可能的响应。用户可以选择其中一个链接并前往该位置。
    **状态:**

    ```html
    300 Multiple Choice
    ```

*   **301 永久移动:****301 永久移动**意味着请求的资源已经永久移动到新的网址。新的网址在回复中给出。
    **状态:**

    ```html
    301 Moved Permanently
    ```

*   **302 找到:****302 找到**意味着请求的资源已经被临时移动到新的网址。访问者在将来的请求中应该使用相同的网址。
    **状态:**

```html
302 Found
```

*   **303 参见其他:**可以在替代网址下找到请求的资源。这是由服务器发送的，目的是将访问者引导到另一个网址，以获取所请求的页面。
    **状态:**

    ```html
    303 See Other
    ```

    *   **304 未修改:**此响应表明，自访问者上次请求以来，请求的页面未被修改。
    **状态:**

    ```html
    304 Not Modified
    ```

    *   **305 使用代理:**T3】305 使用代理是不推荐使用的状态代码。这个响应是由服务器发送的，以便位置头中提到的代理可以访问请求的网址。
    **状态:**

    ```html
    305 Use Proxy
    ```

    *   **306 交换机代理:**此响应代码不再使用。但是，该代码被保留，因为它在以前的版本中使用过。
    **状态:**

    ```html
    306 Switch Proxy
    ```

    *   **307 Temporary Redirect:** The **307 temporary redirect** means that the requested resource has been moved temporarily to a new URL. It shares the same semantics as of 302 Found, with the exception that the user agent must not change the HTTP method used.
    **Status:**

    ```html
    307 Temporary Redirect
    ```

    **支持的浏览器:**与 **HTTP 状态代码重定向响应**兼容的浏览器如下。

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   火狐浏览器
    *   旅行队
    *   歌剧