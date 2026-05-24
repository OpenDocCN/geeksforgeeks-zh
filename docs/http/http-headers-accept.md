# HTTP 头|接受

> 原文:[https://www.geeksforgeeks.org/http-headers-accept/](https://www.geeksforgeeks.org/http-headers-accept/)

**HTTP 接受头**是请求类型头。接受头用于由客户机通知服务器，客户机可以理解哪种内容类型，表示为 MIME 类型。通过使用内容协商，服务器选择内容类型的提议，并用[内容类型](https://www.geeksforgeeks.org/http-headers-content-type/)响应报头通知客户端它的选择。如果请求中没有“接受”头，则服务器认为客户端接受所有类型的媒体。

**语法:**

```html
Accept: <MIME_type>/<MIME_subtype> | <MIME_type>/* | */*
```

**指令:**该标题接受下述指令:

*   **<MIME _ type>/<MIME _ subtype>:**该指令保存客户端将通过内容类型头接收的网络内容的类型/子类型，该内容类型头由服务器从接受头中选择。基本上，它包含单一的 mime 类型，如文本/html。
*   **< MIME_type > /*:** 该指令保持类型，但可以接受任何子类型，如 image/*表示图像可以是 jpg、png 或 can svg 一切都将被接受。
*   ***/*** 本指令接受任何类型/子类型。

**示例:**

*   本示例接受 html 子类型的文本类型。

    ```html
    Accept: text/html
    ```

*   这个例子接受任何图像子类型都不麻烦。

    ```html
    Accept: image/*
    ```

要检查此“接受”操作，请转到**检查元素- >网络**检查“接受”的请求标题，如下所示，“接受”高亮显示，您可以看到。
T3】

**支持的浏览器:**兼容 **HTTP 接受头**的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧