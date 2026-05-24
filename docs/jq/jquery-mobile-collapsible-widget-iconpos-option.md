# jQuery 移动可折叠小部件图标选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-可折叠-widget-iconpos-option/](https://www.geeksforgeeks.org/jquery-mobile-collapsible-widget-iconpos-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。本文将使用 jQuery 移动可折叠小部件图标选项来设置图标在可折叠标题中的位置。它接受字符串值，默认值为“左”。

**语法:**

```html
$( ".selector" ).collapsible({
    iconpos: string
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
                iconpos: "right"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Collapsible Widget iconpos Option</h3>
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

![](img/547709fd158f007fd5b3fb0d94b4f098.png)

**参考:**T2】https://api.jquerymobile.com/collapsible/#option-iconpos