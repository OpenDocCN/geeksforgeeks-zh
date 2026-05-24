# 如何使用 jQuery Mobile 制作列表分隔符有序列表视图？

> 原文:[https://www . geeksforgeeks . org/如何制作列表-分隔符-有序-列表视图-使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-make-list-dividers-ordered-listviews-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 **jQuery Mobile** 创建列表分隔符有序列表视图。

**方法:**首先，添加项目所需的 jQuery 移动脚本。

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

        <h4>
            List divider Ordered listview 
            using jQuery Mobile
        </h4>
    </center>

    <ol data-role="listview" data-divider-theme="d">
        <li data-role="list-divider">1st</li>
        <li>one</li>
        <li>two</li>
        <li data-role="list-divider">2nd</li>
        <li>three</li>
        <li>four</li>
    </ol>
</body>

</html>
```

**输出:**

![](img/eeb1f8c9393df51bca84ea169700b816.png)