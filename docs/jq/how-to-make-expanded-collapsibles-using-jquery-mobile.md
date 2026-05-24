# 如何使用 jQuery Mobile 制作扩展拼贴？

> 原文:[https://www . geeksforgeeks . org/如何制作-展开-折叠-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-expanded-collapsibles-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建扩展的可折叠。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
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

        <h4>
            Expanded collapsible using 
            jQuery Mobile
        </h4>
    </center>

    <div data-role="collapsible" 
        data-collapsed="false">

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

![](img/6f81982b2cb81cf8d098536c370f6fb4.png)