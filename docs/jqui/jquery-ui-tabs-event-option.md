# jQuery 用户界面标签事件选项

> 原文:[https://www.geeksforgeeks.org/jquery-ui-tabs-event-option/](https://www.geeksforgeeks.org/jquery-ui-tabs-event-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 选项卡小部件帮助我们将一些内容放在不同的选项卡中，并允许我们在它们之间切换。在本文中，我们将看到如何在 jQuery UI 滑块中使用**事件选项**。
**事件选项**是让用户在 jQuery UI 中选择新标签页的事件名称。默认情况下，值为**【点击】**

**语法:**

```html
$( ".selector" ).tabs(
   { event : 'click'}
);
```

**参数:**此动作不接受任何参数。

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">

    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">

    <script src=
        "https://code.jquery.com/jquery-1.10.2.js">
    </script>

    <script src=
        "https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function () {
            $("#gfg").tabs({
                event: 'mouseover'
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs event option</h3>

    <div id="gfg">
        <ul>
            <li><a href="#gfg1">Tab 1</a></li>
            <li><a href="#gfg2">Tab 2</a></li>
            <li><a href="#gfg3">Tab 3</a></li>
        </ul>
        <div id="gfg1">
            <p>tab Number -1</p>
        </div>

        <div id="gfg2">
            <p>tab Number -2</p>
        </div>

        <div id="gfg3">
            <p>tab Number -3</p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/c756e0d24743699070aafef691968bc2.png)