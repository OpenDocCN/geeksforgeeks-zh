# 如何使用 CSS 设置图标颜色、大小和阴影的样式？

> 原文:[https://www . geesforgeks . org/how-style-icon-color-size-and-shadow-by-CSS/](https://www.geeksforgeeks.org/how-to-style-icon-color-size-and-shadow-by-using-css/)

**< i >标签和< span >标签**广泛用于在网页上添加图标。要在网页上添加任何图标，它需要标题标签内的 fontawesome 链接。fontawesome 图标可以通过在图标名称前使用 **fa** 前缀来放置。

**fontawesome 链接:**

> https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css

**注意:**无需下载或安装。

**示例 1:** 本示例使用 CSS 设置图标的大小、颜色和阴影。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Font Awesome Icons</title>

    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <style>
        h1 {
            color: Green;
            text-shadow: 2px 3px 6px lime;
        }
        .icons {
            color: red;
        }
        i {
            text-shadow: 2px 4px 6px orange;
        }
        .fa{
            font-size: 50px;
        }
    </style>
</head>

<body style = "text-align:center;">

    <div class = "icons">

        <h1>GeeksforGeeks</h1>

        <i class="fa fa-cloud"></i>
        <i class="fa fa-car"></i>
        <i class="fa fa-road"></i>
        <i class="fa fa-fire"></i>
        <i class="fa fa-bolt"></i>
        <i class="fa fa-apple"></i>
        <i class="fa fa-ambulance"></i>
    </div>
</body>

</html>                           
```

**输出:**
![](img/f1960f7d3b49d56ad4a0b33adcd6e33e.png)

**示例:2** 本示例通过在图标名称后使用 fa-spin 使图标旋转和脉动。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Font Awesome Icons</title>

    <link rel="stylesheet" href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <!-- CSS style to set the icon -->
    <style>
        h1 {
            color: Green;
            text-shadow: 2px 3px 6px lime;
        }
        .icons {
            color: green;
            width: 500px;
            height: 200px;
            border: 5px solid green;
        }
        i {
            text-shadow:2px 4px 6px cyan;
        }
        .fa {
            font-size:50px;
        }
        .fa-apple, .fa-car {
            font-size:80px;
        }
    </style>
</head>

<body style = "text-align:center;">

    <div class = "icons">

        <h1>GeeksforGeeks</h1>

        <i class="fa fa-spinner fa-pulse"></i>
        <i class="fa fa-car"></i>
        <i class="fa fa-road"></i>
        <i class="fa fa-fire"></i>
        <i class="fa fa-bolt"></i>
        <i class="fa fa-apple"></i>
        <i class="fa fa-star fa-spin"></i>
    </div>
</body>

</html>                    
```

**输出:**
![](img/a91a4a4d34bc819968b7ed7e838335c4.png)