# jQuery 移动可折叠小部件折叠选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-collapsedicon-widget-collapsedicon-option/](https://www.geeksforgeeks.org/jquery-mobile-collapsible-widget-collapsedicon-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 可折叠小部件 collapsedIcon 选项来设置处于折叠状态时可折叠容器标题的图标。它接受字符串或布尔类型的值，默认值为“+”。该字符串包含图标的名称。

**语法:**

```html
$( ".selector" ).collapsible({
    collapsedIcon: string/boolean
});
```

**CDN 链接:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 10 . 2 . min . js”></脚本>
> <脚本 src =//code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js”></脚本>

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">

    <script src="//code.jquery.com/jquery-1.10.2.min.js">
    </script>

    <script src=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("#GFG").collapsible({
                collapsedIcon: "arrow-r"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Collapsible Widget collapsedIcon Option</h3>
        </div>

        <div role="main" class="ui-content">
            <div data-role="collapsible" id="GFG">
                <h3>GeeksforGeeks</h3>
                <p>
                    GeeksforGeeks is a computer science portal
                    for geeks. It contains well written, well
                    thought and well explained computer science
                    and programming articles, quizzes etc.
                </p>

            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/28c44206a5d95d0e527e9638d553e9e9.png)

**参考:**[https://API . jquerymobile . com/collapsed/# option-collapsedIcon](https://api.jquerymobile.com/collapsible/#option-collapsedIcon)