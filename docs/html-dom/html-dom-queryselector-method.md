# HTML DOM querySelector()方法

> 原文:[https://www . geesforgeks . org/html-DOM-query selector-method/](https://www.geeksforgeeks.org/html-dom-queryselector-method/)

HTML 中的 **querySelector()** 方法用于返回与文档中指定的 CSS 选择器匹配的第一个元素。

**注意:**query selector()方法只返回与指定选择器匹配的第一个元素。要返回所有匹配项，请使用[查询选择全部()方法](https://www.geeksforgeeks.org/html-dom-queryselectorall-method/)。

**语法:**

```html
element.querySelector(selectors);
```

选择器是必填字段。它指定一个或多个 CSS 选择器来匹配元素。这些选择器用于根据它们的 id、类、类型等选择 HTML 元素。在多个选择器的情况下，用逗号分隔每个选择器。文档中最先出现的元素是返回的元素。如果选择器匹配一个在文档中多次使用的 id(在每页上应该是唯一的)，那么它将返回第一个匹配的元素。

**返回值:-** 该方法用于返回文档中与指定 CSS 选择器匹配的第一个元素。

**示例:**本示例描述了使用 DOM **querySelector()** 方法为特定选择器选择第一个匹配元素。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM querySelector() Method</title>
</head>

<body style="text-align: center;">
    <h1 style="color: green;">GeeksforGeeks</h1>
    <h2>querySelector() Method</h2>
    <div id="gfg">

<p>This is paragraph 1.</p>

<p>This is paragraph 2.</p>

    </div>
    <button onclick="myFunction()">Try it</button>
    <script>
    function myFunction() {
        var x = document.getElementById("gfg");
        x.querySelector("p").style.backgroundColor = "Green";
        x.querySelector("p").style.color = "white";
    }
    </script>
</body>

</html>
```

**输出:**

![](img/8378f92e059cd6dd933fb1226bdb71fb.png)

DOM 查询选择器()方法

**支持的浏览器:**下面列出了 *querySelector()* 方法支持的浏览器:

*   谷歌 Chrome 4.0
*   Internet Explorer 8.0
*   微软边缘
*   Firefox 3.5
*   opera10.0
*   Safari 3.2