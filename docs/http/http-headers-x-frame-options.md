# HTTP 头| X-框架-选项

> 原文:[https://www.geeksforgeeks.org/http-headers-x-frame-options/](https://www.geeksforgeeks.org/http-headers-x-frame-options/)

HTTP 头用于通过 HTTP 响应或 HTTP 请求传递附加信息。 **X-Frame-Options** 用于防止网站**点击劫持攻击**。它定义了是否允许浏览器在 **<框架>** 、 **< iframe >** 、 **<嵌入>** 或 **<对象>** 中呈现页面。内容安全策略(CSP)中的框架祖先指令废弃了 X 框架选项。

**语法:**

```html
X-Frame-Options: directive
```

**指令:**

*   **否认:**此指令阻止在 **<框架>** 中渲染站点，即站点不能嵌入到其他站点中。
*   **相同原点:**如果框架与页面具有相同的原点，则该指令允许在框架中呈现页面。
*   **allow-from uri:** 这个指令现在已经过时了，不应该使用。现代浏览器不支持它。在这种情况下，页面可以在源自指定 uri 的 **<框架>** 中呈现。

**示例:**

*   **在阿帕奇:**
    要将 X-Frame-Options 发送到所有相同原件的页面，请将其设置为您的站点配置。

```html
Header always set X-Frame-Options "sameorigin"
```

*   打开 httpd.conf 文件并添加以下代码来拒绝该权限

```html
header always set x-frame-options "DENY"
```

*   **在 Nginx 上:**打开服务器配置文件，添加以下代码，只允许来自同一来源

```html
add_header x-frame-options "SAMEORIGIN" always;
```

**支持的浏览器:****X-Frame-Options**支持的浏览器如下:

*   铬
*   微软公司出品的 web 浏览器
*   旅行队
*   火狐浏览器
*   边缘

**注意:**只有 Internet Explorer 和 Microsoft Edge 支持 **allow-from** 指令。