# 如何用框架把一个 HTML 页面分成四部分？

> 原文:[https://www . geeksforgeeks . org/如何使用框架将一个 html 页面分成四部分/](https://www.geeksforgeeks.org/how-to-divide-an-html-page-into-four-parts-using-frames/)

在本文中，我们将学习如何使用 HTML 框架将页面分成四个部分。这可以用来表示页眉、侧边栏、页脚和主要内容。框架是使用<框架>标签创建的。我们将不得不对每个部分使用四个 HTML 文件。

**语法:**

```html
<frameset>
    // frame elements
</frameset>
```

下面的示例将演示创建页面四个部分的方法。

```html
<html>
<frameset rows="10%,80%,10%">
  <frame name="A" src="header.html">
    <frameset cols="80%,20%">
      <frame name="B" src="home.html">
        <frame name="C" src="sidebar.html">
    </frameset>
    <frame name="B" src="footer.html">
      <frameset rows="100%">
      </frameset>
</frameset>
</html>
```