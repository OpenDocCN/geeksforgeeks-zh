# 如何在 HTML 和 CSS 中创建水平导航栏？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-horizontal-navigation-bar-in-html-and-css/](https://www.geeksforgeeks.org/how-to-create-a-horizontal-navigation-bar-in-html-and-css/)

在本文中，我们将尝试水平创建一个导航栏。为了理解这篇文章，我们需要了解一些 HTML 和 CSS 的基础知识。

**方法:**

*   我们将创建导航栏的结构，稍后它将水平显示。
*   我们将在这里使用的标签是 [`<nav>` 标签](https://www.geeksforgeeks.org/html-nav-tag/) 和 [`<ul>` 标签](https://www.geeksforgeeks.org/html-ul-tag/)。这里的 `<nav>` 标签将用作容器中的项目列表，并将用于导航。`<ul>` 也将用于列出用户将导航的项目数量。
*   现在我们有了导航栏的结构。因此，我们将应用 CSS 属性如 `flex` 来使导航栏看起来是水平的。

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            Horizontal Navigation Bar
        </title>
    </head>
    <body>
        <!-- here in nav tag used two classes 
             that is navbar and background-->
        <!-- each class declared in nav tag will be 
             used to design the form using CSS-->
        <nav class="navbar background">
            <!-- we have used list tag that is ul 
                 to list the items-->
            <ul class="nav-list">
                <li><a href="#Car">Car</a></li>
                <li><a href="#file">file</a></li>
            </ul>
            <!-- we have used rightnav in order to design
                 the seachbar properly by using CSS-->
            <div class="rightNav">
          <!-- the value that search bar will take is text -->
                <input type="text" name="search" id="search" />
                <button class="btn btn-sm">Search</button>
            </div>
        </nav>
    </body>
</html>
```