# 如何用HTML、CSS、Javascript创建扩展卡？

> 原文：[https://www.geeksforgeeks.org/how-to-create-expanding-cards-using-html-css-and-javascript/](https://www.geeksforgeeks.org/how-to-create-expanding-cards-using-html-css-and-javascript/)

在本文中，我们将看到如何创建一个扩展卡，点击后显示该卡的扩展视图。为了创建这张卡片，我们将使用HTML、CSS和JavaScript。

**方法：** 在本节中，我们将创建我们的HTML卡的结构。

*   创建一个`class`为`container`的`partition`。
*   在`container`中创建另一个`div`，其`class`为`parts`和`are active`。
*   使用你选择的背景图片为`div`面板设置样式。
*   再创建四个具有相同`class` `segments`的`div`。

## HTML

```html
<!-- Container -->
<div class="container">
    <!-- Div with section and active -->
    <div class="section one active"></div>
    <!-- All another div with section -->
    <div class="section two"></div>
    <div class="section three"></div>
    <div class="section four"></div>
</div>
```