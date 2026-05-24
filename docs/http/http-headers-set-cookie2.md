# HTTP 头| Set-Cookie2

> 原文:[https://www.geeksforgeeks.org/http-headers-set-cookie2/](https://www.geeksforgeeks.org/http-headers-set-cookie2/)

**HTTP Set-cookie2** 是响应类型头，已经废弃。它提供了从客户端向服务器提供和检索状态信息的机制。这个命令的用法通常是由**的[设置 cookie](https://www.geeksforgeeks.org/http-headers-set-cookie/) 的**代替**设置 cookie2 的**。该命令 **cookie2** 的用法被 **RFC 6265** 废弃。

**语法:**

```html
Set-Cookie2: <cookie-name>=<cookie-value> | Comment=<value> | Domain=<domain-value> | 
Max-Age=<non-zero-digit> | Path=<path-value> | Discard | Secure 
```

**注意:**使用多个指令也是可以的，只需要用**冒号“；”分隔即可**和多个饼干之间用**逗号“，**隔开。

**指令:**

*   **< cookie-name > = < cookie-value >:** < cookie-name > refers to the name of the cookie, while < cookie-value > refers to the value of this particular cookie. If the name starting with **$** cannot be used by any available application on the computer.
*   **Note = < Value >:** The **< value >** assigned to **Note** allows the server to record how it intends to use cookies, because cookies are used to retrieve or store data.
*   **Domain = < Domain-value >:** This instruction defines the host that sends cookie. This is an optional instruction.
*   **Path = < Path value >:** This value assigned to cookies specifies all URL sets on the source server to which cookies have been applied.
*   **Max-age = < Non-zero number >:** The value of this constraint is in seconds, that is, the cookie lifetime in seconds, which is a decimal non-negative integer. If this life value is greater than incremental seconds, it means that the user should discard cookie.
*   **Discard:** This code deletes/discards cookies by instructing the user agent to discard cookies. Once the user agent terminates, it will be deleted.
*   **Secure:** When this constraint is written by default, cookie will be sent back directly to the original server without any deviation, so as to maintain confidentiality and privacy.

**示例:**您可能在网络检查元素的标头部分找不到这种类型的设置 cookie，因为它已被 **RFC 6265** 淘汰。请避免使用。

```html
Set-Cookie2:Student="David"; Max-Age=12885; Path="/asdf"; Secure
```

**支持的浏览器:**浏览器与 **HTTP 头集-Cookie2** 不兼容。HTTP 头集-Cokkie2 被 **HTTP 头集-Cookie** 取代。