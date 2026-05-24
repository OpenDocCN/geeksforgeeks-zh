# HTTP 头| X-转发-主机

> 原文:[https://www.geeksforgeeks.org/http-header-x-forwarded-host/](https://www.geeksforgeeks.org/http-header-x-forwarded-host/)

**HTTP X-Forwarded-Host** 头是一个请求类型头，事实上是标准头。该报头用于标识客户端发出的原始请求。因为主机名称和端口在反向代理中不同，所以这次该报头率先识别原始请求。这个标题也可以用于调试，创建基于位置的内容。所以这个标题保留了客户的隐私。这个头的根版本是 HTTP 转发。

**语法:**

```html
X-Forwarded-Host: <host>
```

**指令:**此标题接受如上所述的单一指令，如下所述:

*   **<主机> :** 该指令保存转发服务器的域名。

以下示例说明了 **HTTP X-Forwarded-Host** 标头:
**示例:**

*   在这个例子中，被访问的网站是从提到的主机网站转发的。

    ```html
    X-Forwarded-Host: www.example-cdn.com
    ```

*   在这个例子中转发的主机是 geeksforgeeks cdn 页面。

    ```html
    X-Forwarded-Host: www.cdn.geeksforgeeks.org
    ```

要检查正在运行的转发主机，请转到检查**元素- >网络**检查转发主机的请求头，如下所示。
T3】

**支持的浏览器:**浏览器兼容 **HTTP X-Forwarded-Host** 标头至今未知。