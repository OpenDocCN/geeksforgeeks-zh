# 如何使用 jQuery Mobile 在导航栏中制作页脚？

> 原文:[https://www . geeksforgeeks . org/how-make-footer-in-nav bar-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-footer-in-navbar-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 在导航栏中制作页脚。

**方法:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”/">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>Footer in Navbars using jQuery Mobile</h4>
    </center>

    <div data-role="footer">
        <h1>Footer</h1>

        <div data-role="navbar" />
        <ul>
            <li><a href="https://www.geeksforgeeks.org/">
                One</a>
            </li>

            <li><a href="https://www.geeksforgeeks.org/">
                Two</a>
            </li>
        </ul>
    </div>
</body>

</html>
```

**输出:**

![](img/de6dacf490e33d82f2e5b2dd157bf734.png)