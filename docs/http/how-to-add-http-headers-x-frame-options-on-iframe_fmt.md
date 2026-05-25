# 如何在 iframe 上添加 HTTP 头‘X-Frame-Options’？

> 原文：[https://www.geeksforgeeks.org/how-to-add-http-headers-x-frame-options-on-iframe/](https://www.geeksforgeeks.org/how-to-add-http-headers-x-frame-options-on-iframe/)

**HTML 中的内嵌框架标签：**`iframe` 标签用于在 HTML 文档中显示或嵌入另一个文档。其属性之一 `src` 用于指定要显示的文档的网址。一个网站的 X-frame 选项可能会阻止在另一个网站中显示一个 HTML 文档。

**[框架选项：](https://www.geeksforgeeks.org/http-headers-x-frame-options/)** 框架选项不是 `frame` 或 `iframe` 或任何其他 HTML 标签的属性。它是一个响应头，也称为 HTTP 安全头。这个头告诉浏览器是否在指定的网址中呈现 HTML 文档。这对于防止点击劫持攻击起着重要作用。因此，不能在 HTML 文档的正文中设置 X-Frame 选项。它由请求资源的域设置。可用的 X-Frame 选项有：

*   `deny`：它防止任何 URL 在容器（如 `iframe`、`frame`、`object` 和 `applet`）中呈现。即使页面来自同一个站点，当 X-Frame 选项设置为“拒绝”时，它也不会被渲染。
*   `sameorigin`：允许渲染具有相同来源的页面。同一个网站的页面将被允许显示。
*   `allow-from uri`：它只允许来自指定 `uri` 的 HTML 文档。

人们可以在网站的网页配置中设置 X-Frame 选项，该选项将被加载到 `iframe` 中。

**在 IIS 中配置：**

```html
<httpProtocol>
  <customHeaders>
      <add name="X-Frame-Options" value="sameorigin"/>
  </customHeaders>
</httpProtocol>
```

**用于配置 Apache：**

```html
Header always set X-Frame-Options "sameorigin"
```

**注意：**浏览器 Edge（12 版及以上）、Internet Explorer（8 版及以上）支持 X-Frame-Options 中的 `ALLOW-FROM uri`。