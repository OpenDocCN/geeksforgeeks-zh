# 如何在 HTML5 中设置链接文档中文本的语言？

> 原文:[https://www . geesforgeks . org/如何设置 html5 中链接文档的文本语言/](https://www.geeksforgeeks.org/how-to-set-the-language-of-text-in-the-linked-document-in-html5/)

本文的方法是通过在 HTML 标记中使用 **hreflang** 属性来指定 HTML5 中链接文档的文本语言。这里传递的值(或语言代码)是链接文档的代码。(例如，如果给定链接中的文档/网站是英文的，则 en 作为值传递)。

**语法**

```html
<element hreflang="language_code"> 
```

**示例 1:** 下面的代码说明了 hreflang 属性在 link 元素中的使用。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <link id="linkid" rel="stylesheet"
          type="text/css" href="styles.css" 
          sizes="16*16" hreflang="en-us">
</head>

<body style="text-align:center;">
    <h1>GeeksForGeeks</h1>

    <h2>
        How to specify the language of the 
        text in the linked document in HTML5?
    </h2>
</body>

</html>
```