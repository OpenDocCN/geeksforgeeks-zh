# HTTP 头| X-DNS-预取-控制

> 原文:[https://www . geesforgeks . org/http-headers-x-DNS-prefetch-control/](https://www.geeksforgeeks.org/http-headers-x-dns-prefetch-control/)

X-DNS-预取-控制是一个 HTTP 响应类型的头，它通知浏览器是否要执行 DNS 预取。打开它可能不起作用，因为许多浏览器可能在所有情况下都不支持它。关闭它应该在所有支持的浏览器中禁用。大多数浏览器会忽略这个头，因为它们不做域名系统预取。

像样式表、图像、JavaScript 等文件对象是在后台预先获取的。预取是在后台完成的，因为在需要指定项目或用户单击网址时，可能会处理域名系统，这减少了延迟。

**句法:**

*   ```html
    X-DNS-Prefetch-Control: on
    ```

*   ```html
    X-DNS-Prefetch-Control: off
    ```

**指令:**此标题接受两个指令，如上所述，如下所述:

*   **This instruction allows prefetching the domain name system. If the browser supports this function, the browser will do so when the header is unavailable.**
***   **Off:** This instruction disables DNS prefetching. This is very useful if you don't monitor page references, or if you know you don't want to disclose information to these websites.**

****示例:****

*   ****Specific hostnames force lookup:** By using the rel attribute on the **<link>** component with a link type of DNS-Prefetch, you can force the lookup of certain hostnames without providing specific anchors. In this example, the domain name “www.geeksforgeeks.org” will be pre-resolved.

    ```html
    <link rel="dns-prefetch" href="https://www.geeksforgeeks.org/">
    ```

    同样，链接组件用于解析主机名，但没有完整的网址，只能通过在主机名前添加双斜线:

    ```html
    <link rel="dns-prefetch" href="//www.geeksforgeeks.org/">
    ```** 
*   ****Turn prefetching on and off:** You can also use the HTTP-Equiv parameter on the component to send the X-DNS- prefetch-control header on the server side or from a single file. Forcibly prefetching host names may help, for example, forcing pre-resolution of domain names frequently quoted by the whole website on the homepage of a website, even if they are not used on the homepage.

    ```html
    <meta http-equiv="x-dns-prefetch-control" content="off">
    ```

    ```html
    <meta http-equiv="x-dns-prefetch-control" content="on">
    ```** 

****注意:**就带宽而言，DNS 请求非常小，但对于移动网络来说，延迟可能非常高。**

****支持的浏览器:**以下列出**X-DNS-预取-控制**头文件支持的浏览器:**

**T5】谷歌 ChromeT7】火狐 T9】OperaT11】**