# HTTP 头|跨来源-资源-策略

> 原文:[https://www . geesforgeks . org/http-headers-cross-origin-resource-policy/](https://www.geeksforgeeks.org/http-headers-cross-origin-resource-policy/)

**跨来源-资源-策略**是一个 HTTP 响应类型的头，允许服务器防止返回的源的某些跨来源或跨站点嵌入。它补充了**跨来源读阻塞**(一种用于防止某些跨来源读的机制)，因此它对于 CORB 没有覆盖的资源特别有价值。这也是同源策略的附加层。这有助于减轻推测性的旁道攻击以及跨站点脚本包含攻击。
**跨来源资源策略**是保护图像免受幽灵攻击或受损渲染器的唯一方法。

然而，由于 chrome bug，该响应头有时会中断文件下载，并阻止用户在资源上使用**另存为**和**将图像另存为**。

**语法:**

```html
Cross-Origin-Resource-Policy: same-site | same-origin | cross-site
```

**指令:**该标题接受上述三个指令，描述如下:

*   **同站点:**该指令只允许用户在浏览器识别到他们来自同站点(可注册域)的请求时读取资源。
*   **相同来源:**这个指令只允许用户在浏览器识别到他们来自相同来源([方案、主机、端口])的请求时读取资源。
*   **跨站点:**这个指令允许来自不同站点的用户请求也可以读取资源。

**注意:**如果在跨来源资源检查时设置了标头，那么浏览器将自动拒绝不同来源或站点发出的所有无 cors 请求。

以下示例说明了 **HTTP 跨来源-资源-策略**:

**示例:**

*   在下面的示例中，只有浏览器识别为来自同一站点的请求才被允许读取资源。

    ```html
    Cross-Origin-Resource-Policy: same-site
    ```

*   在下面的示例中，只有浏览器识别为来自同一来源的请求才被允许读取资源。

    ```html
    Cross-Origin-Resource-Policy: same-origin
    ```

**支持的浏览器:**浏览器兼容 **HTTP 跨来源-资源-策略**如下:

*   谷歌 Chrome
*   火狐浏览器
*   旅行队