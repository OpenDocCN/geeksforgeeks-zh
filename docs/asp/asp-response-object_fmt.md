# ASP 响应对象

> 原文：`https://www.geeksforgeeks.org/asp-response-object/`

响应对象用于从服务器发送对客户端请求的响应。它有许多预定义的方法、属性和集合。

它有一些方法、属性和集合。

## 属性

*   `Buffer`：定义是否缓冲页面。
*   `Cache Control`：用于设置代理服务器是否可以缓存HTML输出。
*   `Character set`：用于将字符集的名称附加到Response对象的内容类型标头。
*   `Content Type`：用于设置响应标头对象的HTTP内容类型/子类型。默认值是`text/HTML`。
*   `Expiration`：用于设置页面在浏览器上显示前的过期时长。
*   `Expires Absolute`：用于设置浏览器中缓存页面的过期日期和时间。
*   `is the client certificate`：用于指定客户端是否连接或断开与服务器的连接。
*   `pics`：用于向pics标签响应标头添加一个值。
*   `Status`：用于指定用户返回的ASP页面的状态值。

## 方法

*   `Add Header`：此方法用于为HTTP标头指定新名称，并为HTTP响应提供给定值。
*   `Appendix`：此方法用于将字符串添加到此请求的服务器日志条目的末尾。
*   `Clear`：此方法用于清除或擦除缓冲的HTML输出。
*   `End`：此方法用于确保Web服务器停止处理脚本并返回当前结果。
*   `Refresh`：此方法用于立即发送缓冲的输出。
*   `Redirect`：此方法用于将客户端重定向到不同的URL。
*   `Write`：此方法将指定的字符串写入输出。

## 收藏

*   `Cookie`：用于设置或获取Cookie的值。

## 示例

下面的代码说明了响应对象的不同方法。

### ASP

```vb
<%
    Response.Redirect "https://www.geeksforgeeks.org" 
    Response.AppendToLog "My log message"
    Response.Write("Hello GeeksforGeeks");

    Response.AddHeader "WARNING","Error 404 Not found"
%>
```

### 输出

```vb
GeeksforGeeks
```