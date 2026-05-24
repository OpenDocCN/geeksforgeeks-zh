# 如何使用 jQuery Mobile 制作图标可折叠？

> 原文:[https://www . geesforgeks . org/如何制作-图标-可折叠-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-icon-collapsibles-using-jquery-mobile/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 制作一个可折叠的图标。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

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
        <h4>Icon collapsible using jQuery Mobile</h4>
    </center>

    <div data-role="collapsible"
        data-collapsed-icon="arrow-d"
        data-expanded-icon="arrow-u">

        <h4>GeeksforGeeks</h4>
        <ul data-role="listview">
            <li>Geeks1</li>
            <li>Geeks2</li>
            <li>Geeks3</li>
        </ul>
    </div>
</body>

</html>
```

**输出:**

![](img/c1632737c8dfc51630fb8b8133f93d58.png)