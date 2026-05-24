# 如何在 iframe 上添加 HTTP 头‘X-Frame-Options’？

> 原文:[https://www . geesforgeks . org/how-add-http-headers-x-frame-options-on-iframe/](https://www.geeksforgeeks.org/how-to-add-http-headers-x-frame-options-on-iframe/)

**HTML 中的内嵌框架标签:**iframe 标签用于在 HTML 文档中显示或嵌入另一个文档。其属性之一**‘src’**用于指定要显示的文档的网址。一个网站的 X-frame 选项可能会阻止在另一个网站中显示一个 HTML 文档。

**[框架选项:](https://www.geeksforgeeks.org/http-headers-x-frame-options/)** 框架选项不是**框架**或**框架**或任何其他 HTML 标签的属性。它是一个响应头，也称为 HTTP 安全头。这个头告诉浏览器是否在指定的网址中呈现 HTML 文档。这对于防止点击劫持攻击起着重要作用。因此，不能在 HTML 文档的正文中设置 X-Frame 选项。它由请求资源的域设置。可用的 X-Frame 选项有:

*   **deny:** It prevents any URL from being presented in the container, such as iFrame, frame, object and applet. Even if the page comes from the same site, it will not be rendered when the X-Frame option is set to "Reject".
*   **Same origin:** Allows rendering of pages with the same origin. Pages of the same website will be allowed to be displayed.
*   **allow-from *uri* :** It only allows HTML documents from the specified uri.

人们可以在网站的网页配置中设置 X-Frame 选项，该选项将被加载到 iframe 中。

**在 IIS 中配置写:**

```html
<httpProtocol>
  <customHeaders>
      <add name="X-Frame-Options" value="sameorigin"/>
  </customHeaders>
</httpProtocol>
```

**用于配置阿帕奇:**

```html
Header always set X-Frame-Options "sameorigin"
```

**注意:**浏览器 Edge(12 版及以上)、Internet Explorer(8 版及以上)支持 X-Frame-Options 中的 **ALLOW-FROM uri** 。