# HTTP 标头|电子标签

> 原文:[https://www.geeksforgeeks.org/http-headers-etag/](https://www.geeksforgeeks.org/http-headers-etag/)

**ETag 或实体标签**是一个响应类型的头，它作为一个验证器，让客户端发出条件请求。它通过触发请求头来提高重新验证请求的效率，请求头有助于 web 缓存验证，从而经济地利用网络带宽。

**生成 ETag** 作为特定浏览器资源的标识。每次用户打开相同的资源时，浏览器都会发送一个小令牌来验证浏览器的 HTTP 缓存中已经存在的资源版本是否与网络服务器上的当前版本相匹配。如果资源匹配，那么 web 服务器不需要发送完整的响应。这使得处理速度更快，并节省了数据。

**语法:**

```html
ETag : "etag-value"   (strong validation)
ETag : W/"etag-value"  (weak validation)   
```

**指令:**这个头接受两个指令，如上所述，如下所述:

*   **[etag-value]:** It is a string of ASCII characters in double quotes. Every time the browser resource changes, a new value is generated, and it is unique. There is no HTTP specification about the order in which values are generated. Therefore, the method of value generation completely depends on the webserver.
*   **w/:** This is a symbol of weak verification. Compared with strong validator tags, they are very easy to generate, but they are different when performing the comparison process. Weak comparison holds that two tags are equivalent if their opaque tags match character by character, regardless of whether one or both tags are marked as "weak". In strong comparison, only when two tags match character by character and neither tag is weak can two tags be considered equivalent.

**使用请求头处理 ETag:**

*   [T0】 If-Match header: This is mainly used when multiple agents may work on the same resource, so as to prevent accidental coverage when using methods such as POST, PUT and DELETE. Here, the ETag header value of a specific resource is included in the *If-Match* header to check whether there is any change in the resource when the specified action is executed. *412 Prerequisites failed* If they do not match, an error will be displayed. If the current representation does not completely or partially match the previous request, it can also be used to abort the request.

```html
ETag : "21e92a357b3434b5aa"
If-Match : "21e92a357b3434b5aa"
```

*   **If-none-match Header:** This header is used when the stored response of the specific website visited by the user has expired. Here, the server generates *if there is a mismatch value* for the current version, and compares it with the ETag value stored in the user's browser. If the two values match, the *304 unmodified* status code will be displayed. In this case, weak comparison must be used when comparing entity tags.

```html
If-None-Match : "21e92a357b3434b5aa"
```

**例:**

```html
ETag: "21e92a357b3434b5aa"  (strong validation)
ETag: W/"21e92a457b3434b5aa"  (weak validation)
```

**支持的浏览器:**支持的浏览器有 **HTTP 头| ETag** 头如下: