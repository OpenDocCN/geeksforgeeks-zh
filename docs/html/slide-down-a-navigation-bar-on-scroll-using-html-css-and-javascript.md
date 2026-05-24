# 使用 HTML、CSS 和 JavaScript 在滚动条上向下滑动导航条

> 原文:[https://www . geesforgeks . org/slide-down-a-navigation-bar-on-scroll-using-html-CSS-and-JavaScript/](https://www.geeksforgeeks.org/slide-down-a-navigation-bar-on-scroll-using-html-css-and-javascript/)

![](img/104598290c736dec97bbca278a85ac11.png)

要创建向下滑动的导航栏，您需要使用 HTML、CSS 和 JavaScript。HTML 会让身体的结构好看，CSS 会让它看起来好看。这种滑动导航条在网站上看起来很有吸引力。通过使用 JavaScript，当用户向下滚动时，您可以轻松地使导航栏可滑动。

**创建结构:**在本节中，我们将为向下滑动的导航栏创建一个基本的网站结构，当用户向下滚动页面时，它将显示效果。

*   **制作结构的 HTML 代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Slide Down a Navigation Bar on Scroll
        using HTML CSS and JavaScript
    </title>

    <meta name="viewport"
        content="width=device-width, initial-scale=1">
</head>

<body>

    <!-- logo with tag -->
    <article>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <b>
            A Computer Science
            Portal for Geeks
        </b>

<p>
            How many times were you frustrated while
            looking out for a good collection of
            programming/algorithm/interview questions?
            What did you expect and what did you get?
            This portal has been created to provide
            well written, well thought and well
            explained solutions for selected questions.
        </p>

    </article>

    <!-- Navbar items -->
    <div id="navlist">
        <a href="#">Home</a>
        <a href="#">About Us</a>
        <a href="#">Our Products</a>
        <a href="#">Careers</a>
        <a href="#">Contact Us</a>
    </div>

    <!-- for creating scroll -->
    <div class="scrollable"
        style="padding:15px 15px 4500px;">
    </div>
</body>

</html>
```