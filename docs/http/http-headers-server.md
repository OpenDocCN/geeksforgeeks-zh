# HTTP 头|服务器

> 原文:[https://www.geeksforgeeks.org/http-headers-server/](https://www.geeksforgeeks.org/http-headers-server/)

**HTTP 服务器头**是一个响应类型的头，包含服务器用来处理所有请求的软件的信息。这个标题将只有一些服务器的细节像服务器名称软件像 **sffe** 、 **cloudflare** 等。隐藏所有重要信息，因为这样攻击者更容易攻击该服务器软件。

**语法:**

```html
Server: <product>
```

**指令:**HTTP 服务器头接受上面提到的和下面描述的单个指令:

*   **<产品> :** 该指令包含服务器已经使用的软件名称。

以下示例将说明 HTTP 服务器标题:
**示例:**

*   在本例中，服务器使用的软件名称是 Cloudflare。

    ```html
    server: cloudflare
    ```

*   在这个例子中，服务器名是 Akamai 资源优化器，它也显示了带有这个的[服务器定时头](https://www.geeksforgeeks.org/http-headers-server-timing/)。

    ```html
    server: Akamai Resource Optimizer
    server-timing: cdn-cache; desc=HIT
    server-timing: edge; dur=1
    ```

要检查运行中的服务器，请转到**检查元素- >网络**检查服务器的响应头，如下所示，服务器突出显示。
T3】

**支持的浏览器:**与 **HTTP 服务器头文件**兼容的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧