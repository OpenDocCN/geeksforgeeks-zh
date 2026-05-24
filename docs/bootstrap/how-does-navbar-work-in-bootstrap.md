# nav bar 在 Bootstrap 中是如何工作的？

> 原文:[https://www . geesforgeks . org/how-do-nav bar-in-work-bootstrap/](https://www.geeksforgeeks.org/how-does-navbar-work-in-bootstrap/)

A **Navbar** 是放置在页面顶部的导航标题，这有助于使其更加用户友好，从而使通过网站的导航变得容易，并且用户可以直接搜索他们感兴趣的主题。*。navbar* 类用于创建导航栏。根据设备尺寸，导航条可以伸展或收缩，也就是说，导航条用于通过使用*创建响应性设计。navbar-expand-xl|lg|md|sm* 类。因此，它为网页提供了灵活性。

**前提:**为了理解 navbar 概念，需要 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 、 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 、 [Bootstrap](https://www.geeksforgeeks.org/bootstrap-tutorials/) 的基础知识。

**在 Bootstrap 中实现 Navbar 的分步指南:**

*   **Bootstrap CDN:** 要使用 Bootstrap 提供的代码片段，我们需要在 HTML head 元素中添加以下 CDN 文件。

> <src = " https://code . jquery . com/jquery-3 . 5 . 1 . slim . min . js " integrity = " sha 384-dfxdz 2 htph 0 lssss 5 nctpuj/zy 4c+ogpamofvy 38 mvbne+ibbbvyuew+orcxarkfj " cross origin = " anonymous "</script[

*   用*添加 [<u><导航></u>](https://www.geeksforgeeks.org/html-nav-tag/) 标签。navbar* 和*。**nav bar-expand-LG nav bar-dark BG-dark*类中<体>标记。

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark"></nav>
```

*   要添加品牌标识，我们需要一个*。navbar-brand* 类，将包含图像和 *alt* 属性，如果图像没有正确加载，那么将显示文本。

```html
<a class="navbar-brand" href="#">
```

*   我们需要通过添加*来切换按钮。& *。折叠导航条-折叠*类，点击按钮时显示或隐藏菜单项。*
*   现在，在导航栏中添加导航项目。

**实现:**我们需要以下语法来理解 Navbar 的工作原理:

*   **HTML 导航元素:**HTML 导航元素是一个类似于 HTML div 元素的容器元素。我们使用 HTML 导航元素给我们的网站添加一个导航栏。

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark"></nav>
```

*   **导航条内的导航项目:**使用以下语法在导航条内添加导航项目:-

```html
<a class="nav-link active" href="#">
    Home
    <span class="sr-only">(current)</span>
</a>
<a class="nav-link" href="#">About Us</a>
<a class="nav-link" href="#">Tutorials</a>
<a class="nav-link disabled" href="#" 
    tabindex="-1" aria-disabled="true">
    Disabled
</a>
```

*   **导航链接:**使用以下语法在网页中添加链接:-

```html
<a class="nav-link" href="#">About Us</a>
```

**示例:**此示例说明了引导导航栏。我们已经为网页添加了徽标和一些信息。如果你点击导航条图标，它会以列表形式显示与网页相关的所有信息。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>

    <!-- Bootstrap CDN-->
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
        integrity=
"sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z"
        crossorigin="anonymous" />
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity=
"sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js"
        integrity=
"sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN"
        crossorigin="anonymous">
    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"
        integrity=
"sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV"
        crossorigin="anonymous">
    </script>

    <!--CSS-->
    <style>
        .navbar-image {
            width: 80px;
            height: 80px;
            padding: 10px;
        }
    </style>
</head>

<body>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <a class="navbar-brand" href="#">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png"
                class="navbar-image" 
                alt="GFG logo" />
        </a>
        <button class="navbar-toggler" type="button" 
            data-toggle="collapse" 
            data-target="#navbarNavAltMarkup"
            aria-controls="navbarNavAltMarkup" 
            aria-expanded="false" 
            aria-label="Toggle navigation">

            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" 
            id="navbarNavAltMarkup">
            <div class="navbar-nav ml-auto">
                <a class="nav-link active" href="#">
                    Home <span class="sr-only">(current)</span>
                </a>
                <a class="nav-link" href="#">About Us</a>
                <a class="nav-link" href="#">Tutorials</a>
                <a class="nav-link" href="#">Student</a>
                <a class="nav-link" href="#">Courses</a>
                <a class="nav-link" href="#">Help</a>
            </div>
        </div>
    </nav>

    <div class="jumbotron">
        <div class="container">
            <h1 class="display-3 text-success">GeeksforGeeks</h1>
            <h1 class="display-5">DSA Course</h1>
            <hr class="my-2" />
            <p class="main text-justify">
                The one-stop solution is GeeksforGeeks 
                DSA Self-Paced Course with Lifetime 
                Access is a complete package for you 
                to learn and master all the Data 
                Structure Concepts.
            </p>

            <a class="btn btn-primary btn-md" 
                href="#" role="button">Know more</a>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/5d1d7784823f464ab7cdb786e5316e2b.png)