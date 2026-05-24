# 如何使用 jQuery Mobile 创建过滤器显示有序列表视图？

> 原文:[https://www . geesforgeks . org/how-create-filter-show-ordered-listviews-using-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-filter-reveal-ordered-listviews-using-jquery-mobile/)

**jQuery Mobile** 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个过滤器来显示有序列表视图。

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
        <h4>
            Filter reveal Ordered listview
            using jQuery Mobile
        </h4>
    </center>

    <ol data-role="listview" 
        data-filter-reveal="true" 
        data-filter-placeholder="search" 
        data-filter="true">

        <li>One</li>
        <li>Two</li>
        <li>Three</li>
        <li>Four</li>
        <li>Five</li>
        <li>Six</li>
        <li>Seven</li>
        <li>Eight</li>
        <li>Nine</li>
        <li>Ten</li>
    </ol>
</body>

</html>
```

**输出:**

![](img/31c4497b929e136a6185286ff882c56a.png)