# 完整性属性在 HTML 中有什么用？

> 原文:[https://www . geeksforgeeks . org/什么是完整属性在 html 中的用途/](https://www.geeksforgeeks.org/what-is-the-use-of-integrity-attribute-in-html/)

在本文中，我们将学习在 HTML 中使用完整性属性的目的&还将通过一个例子了解它的实现。HTML 引入了一个新的属性，叫做**“完整性”**。integrity 属性的用途是允许浏览器检查提取的脚本，以确保在发生意外操作时不会加载源代码。它用于检查第三方是否已经更改了资源。

A **子资源完整性(SRI)** 是 w3consortium 开发的一个安全特性，特别是用于控制 CORS 请求。它保证获取的外部脚本不会被第三方更改。它指定资源(源文件)的 base64 编码加密哈希。

**SRI 的工作流程如下:**

*   网页保存哈希值，另一方面，服务器保存。js 文件。
*   现在，浏览器匹配完整性属性的哈希值。
*   最后，如果哈希值匹配，则使用该文件，否则该文件将被阻止。

**语法:**

```html
<element integrity="filehash">
```

**属性:**

*   **filehash:** 表示外部脚本文件的哈希值。

**注意:**完整性属性只能与 [<链接>标签](https://www.geeksforgeeks.org/html-link-tag/)或 [<脚本>](https://www.geeksforgeeks.org/html-script-integrity-attribute/) 标签一起使用。

**示例:**这个示例通过在<脚本>标签中声明 HTML 完整性属性来说明它。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML Integrity Attribute</title>

    <script type="text/javascript" src="my_script.js"
        integrity=
"sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo">
    </script>
</head>

<body style="text-align: center">
    <h1>GeeksForGeeks</h1>
    <h2>HTML Integrity Attribute</h2>
    <br />
    <button>Submit</button>
</body>

</html>
```

**输出:**

![](img/26028d502b13005e072e95ad537ef379.png)