# 如何在 bootstrap 中折叠下拉导航栏时改变字体颜色？

> 原文:[https://www . geesforgeks . org/如何在引导中更改字体颜色下拉列表-折叠时导航栏/](https://www.geeksforgeeks.org/how-to-change-font-color-in-dropdown-navbar-when-collapsed-in-bootstrap/)

Bootstrap 4 是最广泛使用的 CSS 框架之一，与 HTML 和 JavaScript 一起构建交互式网站。Bootstrap 4 提供了多种内置组件、类和实用方法，可用于创建用户友好的 web 应用程序。下面的文章实现了在折叠时更改引导导航栏下拉菜单颜色的目的。

**第一种方法:**第一种方法利用 Bootstrap 类在折叠时改变*导航栏*下拉菜单的颜色。Bootstrap 4 有一个内置类。当下拉菜单展开时，显示添加到*导航栏*的项目，当下拉菜单折叠时，该类被隐藏。下拉菜单的颜色可以通过*显示*类来改变。

**代码实现:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
        integrity=
"sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
        crossorigin="anonymous">

    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
        integrity=
"sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
        crossorigin="anonymous">
    </script>

    <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
        integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
        crossorigin="anonymous">
    </script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
        integrity=
"sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
        crossorigin="anonymous">
    </script>

    <style type="text/css">
        .nav-item.dropdown.show a {
            color: blue !important;
        }

        #navbarDropdown {
            color: pink;
        }
    </style>
</head>

<body>
    <nav class="navbar navbar-expand-lg 
        navbar-light bg-light">

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
                    <a class="nav-link" href="#">Home </a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" 
                        href="#" id="navbarDropdown" role="button"
                        data-toggle="dropdown" aria-haspopup="true"
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
        </div>
    </nav>
</body>

</html>
```