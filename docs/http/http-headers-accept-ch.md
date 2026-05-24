# HTTP 头|接受-CH

> 原文:[https://www.geeksforgeeks.org/http-headers-accept-ch/](https://www.geeksforgeeks.org/http-headers-accept-ch/)

**HTTP Accept-CH** 头是一个响应类型的头，表示服务器可以支持的客户端提示，并且应该包含在进一步的请求中。

**语法:**

```html
Accept-CH: client hints
```

**注意:**客户端提示可以不止一个，用逗号隔开。

**指令:**HTTP Accept-CH 头接受一个指令，如上所述，如下所述:

*   **客户端提示:**该指令包含一组用于主动内容协商的 HTTP 请求头字段，用于指示设备和代理特定首选项的列表。

下面的例子将说明**HTTP accept-CH**头:

**示例:**

*   当使用一个客户端提示时。在本例中，视口宽度是客户端提示，它以 CSS 像素表示布局视口宽度。

    ```html
    Accept-CH: Viewport-Width
    ```

*   当使用多个客户端提示时。在本例中，视口宽度和宽度是客户端提示。

    ```html
    Accept-CH: Viewport-Width, Width
    ```

要检查运行中的接受通道，请转到**检查元件- >网络**检查接受通道的响应头，如下所示。
T3】

**支持的浏览器:**浏览器兼容 **HTTP Accept-CH 头**如下:

*   谷歌 Chrome
*   歌剧