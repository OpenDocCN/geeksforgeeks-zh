# HTTP 头| Pragma

> 原文:[https://www.geeksforgeeks.org/http-headers-pragma/](https://www.geeksforgeeks.org/http-headers-pragma/)

**Pragma** 是 HTTP/1.0 报头中的无缓存通用类型 CORS 安全列表响应报头字段，用于请求-响应链。一个 pragma 头意味着阻止客户端缓存响应，pragma 意味着浏览器告诉服务器和任何中间缓存它想要一个资源的新版本，反之亦然，这是不正确的。

**注意:** **没有为 HTTP 响应指定 Pragma** ，这就是为什么它不能可靠地替代一般的 HTTP/1.1 Cache-Control 头。它仅用于向后兼容 HTTP/1.0 客户端。

**Pragma 和缓存控制头的区别:****Pragma**仅定义为适用于客户端的请求，而**缓存控制**可用于客户端的请求和服务器的响应。

**语法**

```html
Pragma: no-cache
```

**指令:**同**缓存控制:无缓存**表头。它强制缓存在释放缓存副本之前将请求提交给源服务器进行验证。

**示例:**

```html
Pragma: no-cache
```

要检查正在运行的实用程序，请转到**检查元素- >网络**检查实用程序的标题，如下所示。Pragma 标题突出显示。
T3】

**浏览器兼容性:**与 **Pragma 头文件**兼容的浏览器如下:

*   谷歌 chrome 6.0 及以上版本
*   Internet Explorer 9.0 及以上版本
*   Firefox 4.0 及以上版本
*   Opera 11.1 及以上
*   Safari 5.0 及以上版本
*   三星互联网