# HTTP 头|内容-位置

> 原文:[https://www . geesforgeks . org/http-headers-content-location/](https://www.geeksforgeeks.org/http-headers-content-location/)

**HTTP 内容-位置**头是一个实体头，它为返回的数据提供了另一个位置，并通过指示直接的网址来告诉如何访问资源。它的用法经常与另一个 HTTP 头位置混淆。它们之间的主要区别是位置给出了页面重定向发生的资源的网址，而 **HTTP Content-Location** 用于指示传输资源的网址。

**语法:**

```html
Content-Location: <url>
```

**指令:**该标题接受上面提到的和下面描述的单个指令:

*   **< url > :** 该指令保存访问资源的相对或绝对 url。

**示例:**

*   在本例中，index.html 是指示内容位置的网址。

    ```html
    Content-Location: /index.html
    ```

    *   In this example, teddy.xml is the URL which indicates the location of the content.

    ```html
    Content-Location: /teddy.xml
    ```

    要检查此内容位置是否有效，请转到**检查元素- >网络**检查内容位置的响应头，如下所示。
    T3】

    **支持的浏览器:**浏览器兼容 **HTTP 内容-位置**标题如下:

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   歌剧
    *   火狐浏览器
    *   旅行队