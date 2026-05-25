# HTTP 头 | X-Frame-Options

> 原文: [https://www.geeksforgeeks.org/http-headers-x-frame-options/](https://www.geeksforgeeks.org/http-headers-x-frame-options/)

HTTP 头用于通过 HTTP 响应或 HTTP 请求传递附加信息。`X-Frame-Options` 用于防止网站`点击劫持攻击`。它定义了是否允许浏览器在`<frame>`、`<iframe>`、`<embed>`或`<object>`中呈现页面。内容安全策略(CSP)中的`frame-ancestors`指令废弃了`X-Frame-Options`。

## 语法:

```html
X-Frame-Options: directive
```

## 指令:

*   `DENY`: 此指令阻止在`<frame>`中渲染站点，即站点不能嵌入到其他站点中。
*   `SAMEORIGIN`: 如果框架与页面具有相同的原点，则该指令允许在框架中呈现页面。
*   `allow-from uri`: 这个指令现在已经过时了，不应该使用。现代浏览器不支持它。在这种情况下，页面可以在源自指定 URI 的`<frame>`中呈现。

## 示例:

### 在 Apache 上:
要将 `X-Frame-Options` 发送到所有相同原点的页面，请将其设置为您的站点配置。

```html
Header always set X-Frame-Options "SAMEORIGIN"
```

打开 `httpd.conf` 文件并添加以下代码来拒绝该权限

```html
Header always set X-Frame-Options "DENY"
```

### 在 Nginx 上:
打开服务器配置文件，添加以下代码，只允许来自同一来源

```html
add_header X-Frame-Options "SAMEORIGIN" always;
```

## 支持的浏览器:
`X-Frame-Options` 支持的浏览器如下:

*   Chrome
*   Internet Explorer
*   Safari
*   Firefox
*   Edge

## 注意:
只有 Internet Explorer 和 Microsoft Edge 支持 `allow-from` 指令。