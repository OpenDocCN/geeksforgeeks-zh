# HTTP Link头字段

> 原文：[https://www.geeksforgeeks.org/http-headers-link/](https://www.geeksforgeeks.org/http-headers-link/)

对于在HTTP头中序列化一个或多个链接，使用`HTTP Link`头字段。它允许服务器将感兴趣的客户端指向另一个包含所请求资源的元数据的资源。它在语义上相当于HTML `<link>`元素。

## 语法

```
Link: <uri-reference>; param1="value1" param2="value2"
```

## 指令

该标题接受如上所述和如下所述的单个指令。链接头包含参数，用`;`分隔，并且相当于`<link>`元素的属性。

*   `<uri-reference>`：URI参考，必须包含在`<`和`>`之间。

## 示例

*   这意味着在相对URI为`https://www.geeksforgeeks.org/`的资源中可以获得关于所请求资源的更多信息。

```
Link: <https://www.geeksforgeeks.org/>; rel="preconnect"
```

*   URI必须包含在`<`和`>`之间。所以，这不是一个好的写作方式。

```
Link:https://www.geeksforgeeks.org/; rel="preconnect"
```

## 指定多个链接

可以指定多个链接，用逗号分隔。

### 示例

```
Link: <https://example.one.com>; rel="preconnect", 
<https://example.two.com>; rel="preconnect", 
<https://example.three.com>; rel="preconnect"
```

## 典型用途

*   不同语言、内容类型和特定版本的URIs地图
*   授权，如知识共享
*   有关如何编辑文件的信息
*   关于数据的适当使用和/或分发的政策信息

## 支持的浏览器

`HTTP-header Link`支持的浏览器至今未知。