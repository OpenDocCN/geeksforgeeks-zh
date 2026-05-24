# ASP 缓存控制属性

> 原文:[https://www.geeksforgeeks.org/asp-cachecontrol-property/](https://www.geeksforgeeks.org/asp-cachecontrol-property/)

**ASP 缓存控制属性**用于设置代理服务器是否可以缓存 ASP 生成的 HTML 输出。代理服务器被配置为缓存网页以加快响应时间。基本上，ASP 页面被开发为对每个用户都是唯一的，或者可能包含安全信息。默认情况下，代理服务器不会存储缓存副本。

**语法**

```vb
response.CacheControl[=control_header]

```

**参数值:**该属性接受如上所述的单个参数，如下所述:

**control_header:** 它指定了一个缓存控制头，可以进一步设置为两个值——缓存控制的值是字符串，必须用引号(" ")括起来。

1.  **Public:** It specifies a cache type to be shared with any user. If a proxy server is used, the page will be cached with this setting.
2.  ****Private** : **It h** is the default value. It only shares cached pages with specific users. Most proxy servers do not cache pages with this setting.**

****例 1:****

## **超文本标记语言**

```vb
// Property set to Public cache
<% response.CacheControl="Public" %>
```

****示例 2:****

## **HTML**

```vb
// Property set to private cache 
<% response.CacheControl="Private" %>
```