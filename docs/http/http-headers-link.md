# HTTP 头|链接

> 原文:[https://www.geeksforgeeks.org/http-headers-link/](https://www.geeksforgeeks.org/http-headers-link/)

对于在 HTTP 头中序列化一个或多个链接，使用 **HTTP 链接头字段**。它允许服务器将感兴趣的客户端指向另一个包含所请求资源的元数据的资源。它在语义上相当于 HTML **<链接>** 元素。
**语法:**

```html
Link: <uri-reference>; param1="value1" param2="value2"

```

**指令:**该标题接受如上所述和如下所述的单个指令。链接头包含参数，用；并且相当于<链接>元素的属性。

*   **<uri-reference>:**URI 参考，必须包含在<和>之间。

**示例:**

*   这意味着在相对 URI 为**https://www.geeksforgeeks.org/.**的资源中可以获得关于所请求资源的更多信息

```html
Link: <https://www.geeksforgeeks.org/>; rel="preconnect"

```

*   URI 必须包含在< and >之间。所以，这不是一个好的写作方式。

```html
Link:https://www.geeksforgeeks.org/; rel="preconnect"

```

**指定多个链接:**可以指定多个链接，用逗号分隔。

**示例:**

```html
Link: <https://example.one.com>; rel="preconnect", 
<https://example.two.com>; rel="preconnect", 
<https://example.three.com>; rel="preconnect"

```

**典型用途为:**

*   不同语言、内容类型和特定版本的 URIs 地图
*   授权，如知识共享
*   有关如何编辑文件的信息
*   关于数据的适当使用和/或分发的政策信息

**支持的浏览器:**HTTP-header 链接支持的浏览器至今未知。