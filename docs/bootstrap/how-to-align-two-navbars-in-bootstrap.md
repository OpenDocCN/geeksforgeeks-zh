# 如何在 bootstrap 中对齐两个中杠？

> 原文:[https://www . geeksforgeeks . org/如何对齐引导中的两个导航条/](https://www.geeksforgeeks.org/how-to-align-two-navbars-in-bootstrap/)

Navbar 是 web 应用程序的一部分，允许用户导航到网站的不同部分。顾名思义，navbar 基本上就是一个导航栏。Bootstrap 4 提供了一个内置的 *navbar* 类，允许我们创建 navbar。此外，我们可以通过根据我们的需求定义各种 CSS 样式来创建自定义导航栏。在本文中，我们将演示使用 CSS 内置类和自定义 CSS 样式对齐两个导航栏的方法。

**示例 1:** 在第一种方法中，我们使用了 Bootstrap 4 的内置*导航栏*类。两个中杠一个接一个地放置。第一个导航栏有一个黑色背景，导航链接是左对齐的，而“注册”和“注销”按钮是右对齐的。第一个 navbar 还包括一个下拉菜单，其中包含指向网站几个部分的链接。第二个导航栏中的导航链接向右对齐，明文中的超链接向左对齐。两个导航条都与屏幕尺寸相关。当屏幕尺寸减小时，导航条切换按钮出现，当屏幕尺寸增大时，导航条切换按钮消失。单击切换按钮时会显示导航栏。

**代码实现:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>

    <!--import bootstrap cdn-->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
        crossorigin="anonymous">

    <!--import jquery cdn-->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" 
        integrity=
"sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.bundle.min.js"
        integrity=
"sha384-ho+j7jyWK8fNQe+A12Hb8AhRq26LrZ/JpcUGGOn+Y7RsweNrtN/tE3MoK7ZeZDyx"
        crossorigin="anonymous">
    </script>
</head>

<body>

    <!--First navbar-->
    <nav class="navbar navbar-expand-lg 
                navbar-dark bg-dark">

        <a class="navbar-brand" href="#">Navbar</a>

        <button class="navbar-toggler" type="button"
            data-toggle="collapse" 
            data-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent" 
            aria-expanded="false" 
            aria-label="Toggle navigation">

            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" 
                id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                    <a class="nav-link" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" 
                        href="#" id="navbarDropdown"
                        role="button"
                        data-toggle="dropdown" 
                        aria-haspopup="true" 
                        aria-expanded="false">
                        Dropdown
                    </a>

                    <div class="dropdown-menu" 
                        aria-labelledby="navbarDropdown">
                        <a class="dropdown-item" href="#">
                            Action
                        </a>

                        <a class="dropdown-item" href="#">
                            Another action
                        </a>

                        <div class="dropdown-divider"></div>
                        <a class="dropdown-item" href="#">
                            Something else here
                        </a>
                    </div>
                </li>
            </ul>

            <button class="btn btn-success my-2 
                my-sm-0 mx-2" type="submit">
                Register
            </button>

            <button class="btn btn-danger my-2 
                my-sm-0" type="submit">
                Logout
            </button>
        </div>
    </nav>

    <!--Second navbar-->
    <nav class="navbar navbar-expand-lg 
        navbar-light bg-light">

        <button class="navbar-toggler" 
            type="button" data-toggle="collapse" 
            data-target="#navbarNavAltMarkup"
            aria-controls="navbarNavAltMarkup" 
            aria-expanded="false" 
            aria-label="Toggle navigation">

            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" 
            id="navbarNavAltMarkup">
            We have changed our Privacy 
            Policy. To know more
            <a href="#" class="mx-1">click here</a>.

            <ul class="navbar-nav ml-auto">
                <li class="nav-item nav-link" 
                    href="#">About Us
                </li>

                <li class="nav-item nav-link" 
                    href="#">Contact Us
                </li>

                <li class="nav-item nav-link" 
                    href="#">Explore
                </li>
            </ul>
        </div>
    </nav>
</body>

</html>
```