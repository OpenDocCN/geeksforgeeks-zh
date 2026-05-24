# HTTP 头|想要的摘要

> 原文:[https://www.geeksforgeeks.org/http-headers-want-digest/](https://www.geeksforgeeks.org/http-headers-want-digest/)

在讨论 **HTTP 想要-摘要头**之前，我们先来了解一下什么是摘要(或者消息摘要)？ **[HTTP 头摘要](https://www.geeksforgeeks.org/http-headers-digest/)** 是使用哈希函数生成的消息的加密固定大小表示。哈希函数可以是将任意大小的数据映射到固定大小的任何函数。消息摘要很容易加密，但很难解密。可以说这个过程是不可逆的。因此，消息摘要可以保护消息的完整性，并可以轻松检测消息中的任何修改。各种类型的散列算法被用于加密这些消息。

**HTTP 想要的摘要头:****HTTP 想要的摘要头**是一个通用的 HTTP 头，它请求服务器使用 HTTP 摘要响应头来提供所请求的源的摘要。请求者发送一个或多个摘要算法，这些算法可用于在报头中创建摘要。如果服务器不支持这些算法，要么使用一些不同的算法计算摘要，要么接收到一个 **400 错误请求**，并在另一个 **HTTP 想要的摘要标题**中列出支持的算法。

**语法:**

*   For a single algorithm:

    ```html
    Want-Digest: <algorithm>
    ```

*   Add quality value syntax to multiple algorithms:

    ```html
    Want-Digest: <algorithm><q-value>, <algorithm><q-value>
    ```

**注意:**这个表头可以包含多个摘要算法。

**指令:****HTTP Want-Digest 头**接受上面提到的下面描述的两个指令:

*   **< Algorithm >:** This instruction holds algorithms that support summarization algorithms including SHA-256, MD5 and SHA-512.
*   **< Q value >:** This instruction saves the quality factor associated with the algorithm to indicate the preference of the algorithm. It ranges from 0 to 1, where 1 is the highest priority.

**示例:**

*   This example holds a single summarization algorithm, but there is no quality value of this algorithm.

    ```html
    Want-Digest: sha-512
    ```

*   This example holds several summarization algorithms with the algorithm quality values.

    ```html
    Want-Digest: sha-512;q=0.55, sha-256;q=0, md5;q=1
    ```

**支持的浏览器:**浏览器兼容 **HTTP Want-Digest 头**列表如下: