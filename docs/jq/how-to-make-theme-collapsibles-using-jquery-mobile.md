# 如何使用 jQuery Mobile 制作主题拼贴？

> 原文:[https://www . geesforgeks . org/how-to-make-theme-collapsables-use-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-theme-collapsibles-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个可折叠的主题。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src = " http://code . jquery . com/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本 src = " http://code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js "></脚本>

**例 1:**

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
            Theme collapsible using 
            jQuery Mobile
        </h4>
    </center>

    <div data-role="collapsible" 
        data-theme="b">

        <h4>GeeksforGeeks</h4>
        <p>This content is collapsible</p>
    </div>
</body>

</html> 
```

**输出:**

![](img/5aee04265f6ff0e72c7ae691056c493a.png)