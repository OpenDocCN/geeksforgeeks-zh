# HTML DOM Range endContainer 属性

> 原文:[https://www . geesforgeks . org/html-DOM-range-end container-property/](https://www.geeksforgeeks.org/html-dom-range-endcontainer-property/)

**endContainer** 属性返回当前范围**结束**的**节点**。这是只读属性。

**语法:**

```html
parentNode = range.endContainer;

```

**返回值:**

*   返回当前范围结束的节点。

**示例:**这个示例将展示如何获取当前范围的 endContainer 节点。

## 超文本标记语言

```html
<html>
<head>
<title>HTML DOM range endContainer property</title>   
</head>
<body>
    <h1>GeeksforGeeks</h1>

<p>This is the Range Content</p>

</body>
<script>
    let range = document.createRange();
    let referenceNode = document.getElementsByTagName('p').item(0);
    range.selectNode(referenceNode);
    console.log(range.endContainer);
</script>
</html>
```

**输出:**在控制台中，我们得到了我们范围内的 endContainer 节点。

![](img/06731fe319be386c9e95d2f5f60f28d6.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器