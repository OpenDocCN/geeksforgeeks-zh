# HTTP 头| X-内容-类型-选项

> 原文:[https://www . geesforgeks . org/http-headers-x-content-type-options/](https://www.geeksforgeeks.org/http-headers-x-content-type-options/)

**HTTP 头 X-内容类型-选项**作为一个标记，指示内容类型头中的 MIME 类型头不应更改为服务器。这个标题是在微软的 Internet Explorer 8 中引入的。此标头阻止内容嗅探(不可执行的 MIME 类型转换为可执行的 MIME 类型)。之后，所有其他浏览器也引入了 X-Content-Type-Options，它们的 MIME 嗅探算法也没有那么激进。

**语法:**

```html
x-content-type-options: nosniff
```

**指令:**X-内容-类型-选项头接受单个指令。

*   **nosniff:** 如果有“样式”MIME 类型不是**文本/css** 和 **JavaScript MIME 类型**，它会阻止所有请求。此外，如果有 MIME 类型的**文本/html** 、**文本/纯文本**、**文本/jason** 、**应用程序/jason** 和任何类型的 **xml** 扩展，它还会启用交叉起源。

**示例:**

```html
x-content-type-options: nosniff
```

要检查运行中的**X-内容-类型-选项**，请转到检查**元素- >网络**检查 X-内容-类型-选项的请求标题，如下所示。

![](img/5c493396b09f8a0f6834fe08eb5abb5b.png)

**支持的浏览器:**兼容**x-内容-类型-选项**标题的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧