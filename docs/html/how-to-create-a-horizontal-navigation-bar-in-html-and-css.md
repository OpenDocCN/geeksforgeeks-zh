# 如何在 HTML 和 CSS 中创建水平导航栏？

> 原文:[https://www . geesforgeks . org/如何创建 html 和 css 中的水平导航栏/](https://www.geeksforgeeks.org/how-to-create-a-horizontal-navigation-bar-in-html-and-css/)

在本文中，我们将尝试水平创建一个导航栏。为了理解这篇文章，我们需要了解一些 HTML 和 CSS 的基础知识。

**方法:**

*   We will create the structure of the navigation bar, which will be displayed horizontally later.
*   The tags we will use here are [< navigation > tag](https://www.geeksforgeeks.org/html-nav-tag/) and [< UL > tag](https://www.geeksforgeeks.org/html-ul-tag/) . The navigation label here will be used as a list of items in a container and will be used for navigation. Ul will also be used to list the number of items that users will navigate.
*   Now we have the structure of the navigation bar. So we will apply CSS attributes like flex to make the navigation bar look horizontal.

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