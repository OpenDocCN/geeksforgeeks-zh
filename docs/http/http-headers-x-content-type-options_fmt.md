# HTTP 头：X-Content-Type-Options

> 原文：[https://www.geeksforgeeks.org/http-headers-x-content-type-options/](https://www.geeksforgeeks.org/http-headers-x-content-type-options/)

`X-Content-Type-Options` HTTP 头作为一个标记，指示 `Content-Type` 头中的 MIME 类型不应被服务器更改。这个头部是在微软的 Internet Explorer 8 中引入的。此标头阻止内容嗅探（将不可执行的 MIME 类型转换为可执行的 MIME 类型）。之后，所有其他浏览器也引入了 `X-Content-Type-Options`，它们的 MIME 嗅探算法也没有那么激进。

## 语法

```
x-content-type-options: nosniff
```

## 指令

`X-Content-Type-Options` 头接受单个指令。

*   **nosniff**：如果有“样式” MIME 类型不是 `text/css` 和 `JavaScript MIME types`，它会阻止所有请求。此外，如果有 MIME 类型的 `text/html`、`text/plain`、`text/json`、`application/json` 和任何类型的 `xml` 扩展，它还会启用跨源策略。

## 示例

```
x-content-type-options: nosniff
```

要检查运行中的 `X-Content-Type-Options`，请转到检查 **元素 -> 网络**，检查 `X-Content-Type-Options` 的请求头，如下所示。

![](img/5c493396b09f8a0f6834fe08eb5abb5b.png)

## 支持的浏览器

兼容 `X-Content-Type-Options` 头的浏览器如下：

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧