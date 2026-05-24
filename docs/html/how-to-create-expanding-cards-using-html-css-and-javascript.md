# 如何用 HTML、CSS、Javascript 创建扩展卡？

> 原文:[https://www . geeksforgeeks . org/如何使用-html-CSS-和-javascript 创建-扩展-卡片/](https://www.geeksforgeeks.org/how-to-create-expanding-cards-using-html-css-and-javascript/)

在本文中，我们将看到如何创建一个扩展卡，点击后显示该卡的扩展视图。为了创建这张卡片，我们将使用 HTML、CSS 和 JavaScript。

**方法:**在本节中，我们将创建我们的 HTML 卡的结构。

*   Create a *partition* with *class* container.
*   Create another *div* in the container, and the class *parts* and *are active* .
*   Use the background image you selected to set the style for the *div* panel.
*   Make four more *div* same class segments.

**HTML:**

## HTML

```html
<!-- Container  -->
   <div class="container">
       <!-- Div with section and active -->
       <div class="section one active"></div>
       <!-- All another div with section  -->
       <div class="section two"></div>
       <div class="section three"></div>
       <div class="section four"></div>
   </div>
```