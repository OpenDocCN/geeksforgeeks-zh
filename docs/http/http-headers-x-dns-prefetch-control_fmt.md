# HTTP 头：X-DNS-预取-控制

> 原文：[https://www.geeksforgeeks.org/http-headers-x-dns-prefetch-control/](https://www.geeksforgeeks.org/http-headers-x-dns-prefetch-control/)

`X-DNS-Prefetch-Control` 是一个 HTTP 响应头，用于通知浏览器是否执行 DNS 预取。启用它可能不会生效，因为许多浏览器可能并非在所有情况下都支持此功能。禁用它则应在所有支持的浏览器中生效。大多数浏览器会忽略此头，因为它们不进行 DNS 预取。

样式表、图像、JavaScript 等资源对象会在后台被预先获取。预取在后台进行，因为在需要指定项目或用户点击网址时，DNS 解析可能已经完成，从而减少了延迟。

## 句法

*   `X-DNS-Prefetch-Control: on`
*   `X-DNS-Prefetch-Control: off`

## 指令

此头部接受两个指令，如下所述：

*   **on**：此指令允许预取 DNS。如果浏览器支持此功能，当头部不可用时，浏览器也会执行预取。
*   **off**：此指令禁用 DNS 预取。如果您不监控页面引用，或者您知道不希望向这些网站披露信息，这将非常有用。

## 示例

*   **强制解析特定主机名**：通过在 `<link>` 组件上使用 `rel` 属性，并将链接类型设置为 `dns-prefetch`，您可以强制解析某些主机名，而无需提供特定的锚点。在此示例中，域名 “www.geeksforgeeks.org” 将被预解析。

    ```html
    <link rel="dns-prefetch" href="https://www.geeksforgeeks.org/">
    ```

    同样，链接组件可用于解析主机名，但无需完整的 URL，只需在主机名前添加双斜线：

    ```html
    <link rel="dns-prefetch" href="//www.geeksforgeeks.org/">
    ```

*   **开启和关闭预取**：您还可以在组件上使用 `http-equiv` 参数，从服务器端或单个文件发送 `X-DNS-Prefetch-Control` 头。强制预取主机名可能有所帮助，例如，在网站首页强制预解析整个网站经常引用的域名，即使它们未在首页使用。

    ```html
    <meta http-equiv="x-dns-prefetch-control" content="off">
    ```

    ```html
    <meta http-equiv="x-dns-prefetch-control" content="on">
    ```

## 注意

就带宽而言，DNS 请求非常小，但对于移动网络来说，延迟可能非常高。

## 支持的浏览器

以下列出支持 `X-DNS-Prefetch-Control` 头的浏览器：

*   谷歌 Chrome
*   火狐
*   Opera