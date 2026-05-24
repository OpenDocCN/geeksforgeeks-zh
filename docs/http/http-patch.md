# HTTP 补丁

> 原文:[https://www.geeksforgeeks.org/http-patch/](https://www.geeksforgeeks.org/http-patch/)

**HTTP Patch** 方法用于请求请求实体中的一组修改，以应用于请求-URI 所识别的资源。该方法通过对资源进行部分更改，在提高互操作性和防止错误方面发挥着至关重要的作用。所描述的一组更改通过媒体类型以被标识为*补丁文档*的格式表示。

**补丁**是一种独特的方法，可以应用服务器请求的所有更改，也可以不应用。如果 PATCH 请求是使用缓存传递的，则请求 URI 标识一个或多个缓存的实体。那么这些条目被指定为“陈旧”条目。修补程序文档没有默认格式，需要服务器来创建符合所识别资源需求的文档。此请求方法应该以幂等的方式发出，因为它可以防止两个补丁请求在相似的时间范围内在同一资源上发生冲突而导致不良结果。

**补丁**非常不同，因为服务器处理封闭的实体来修改由请求-URI 标识的资源。包含的实体包含一组说明，描述修改源服务器中现有资源的当前版本的过程。这种方法会影响请求-URI 所标识的资源，并且还可能成为对其他资源产生副作用的原因。

**例:**本例摘自**RFC 5789T5。它描述了修补文档在现有资源上的使用以及现有文本文件收到的成功响应。作为响应，由于缺少消息正文，使用了 204 代码，而 ETag 响应头字段用于表示通过应用 Patch 在*http://www.example.com/file.txt*创建的实体。**

**请求:**T0】

**回应:**

```htmlhtml
HTTP/1.1 204 No Content
   Content-Location: /file.txt
   ETag: "e0023aa4f"

```

**补丁中的错误处理:**

修补程序请求可能会因出现上述任何错误而失败。

1.  **Malformed patch document:** This error will occur when the client sends a malformed patch document. It is specified by the 400 (error request) response.
2.  **Unsupported patch document:** This error occurs when the format of the patch document sent by the client is not supported by the server, because the current resource is identified by the request URI. It is specified by the 415 (unsupported media type) response.
3.  **Unprocessible request:** This error occurs when the server thinks the syntax is valid and understands the document, but cannot process the request. It is specified by the 422 (non-processable entity) response.
4.  **No resources found:** This type of error will occur when **Patch** document cannot be applied to non-existent resources. It is specified by the 404 (not found) response.
5.  **Conflict state:** This error will occur when the request cannot be applied in the given resource state. It is specified by the 409 (conflict) response.
6.  **Conflict modification:** This error occurs when the client fails to define the precondition by using *if-match or If-Unmodified- from* header. It is specified by the 412 (prerequisite failed) response. When the server detects a possible conflict modification and no preconditions are defined in the request, it sends a 409 (conflict) response.
7.  **Concurrent modification:** This error occurs when the server cannot queue concurrent requests to modify resources when it is running under restrictions. It is specified by the 409 (conflict) response. It is specified by the 409 (conflict) response.