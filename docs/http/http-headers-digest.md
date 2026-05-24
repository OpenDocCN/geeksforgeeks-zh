# HTTP 头|摘要

> 原文:[https://www.geeksforgeeks.org/http-headers-digest/](https://www.geeksforgeeks.org/http-headers-digest/)

**摘要 HTTP 头**是一个响应 HTTP 头，它为请求的资源提供了一个由散列函数从整个消息生成的小值。摘要 HTTP 头是一个响应头，它提供了所请求资源的摘要。整个表示用于计算摘要。单个资源的多个摘要值也是可能的，因为表示取决于[内容类型](https://www.geeksforgeeks.org/http-headers-content-type/)和[内容编码](https://www.geeksforgeeks.org/http-headers-content-encoding/)。

**语法:**

```html
Digest:<digest-algorithm>=<digest-value>
```

**指令:**这个头接受两个指令，如上所述，如下所述:

*   **< Summary-algorithm >:** It contains defined supporting algorithms, such as SHA-256 and SHA-512.
*   **< Summary value >:** Save the result of encoding resource representation and applying summary algorithm.

**示例:**

*   It provides the sha-256 algorithm for resources, and also provides the summary value.

    ```html
    Digest: sha-256=nOJRJgeeksforgeeksN3OWDUo9DBPE=
    ```

*   It provides the sha-512 algorithm for resources, and also provides the summary value. In addition, it also provides UNIX summation algorithms affected by conflicts.

    ```html
    Digest: sha-512=\vdtgeeksforgeeks8nOJRJN3OWDDBPE=, unixsum=69
    ```

**支持的浏览器:**浏览器兼容 **HTTP 摘要头**列表如下: