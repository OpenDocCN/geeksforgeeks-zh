# jQuery 用户界面标签可折叠选项

> 原文:[https://www . geesforgeks . org/jquery-ui-tab s-可折叠-option/](https://www.geeksforgeeks.org/jquery-ui-tabs-collapsible-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 选项卡小部件帮助我们将一些内容放在不同的选项卡中，并允许我们在它们之间切换。在本文中我们将看到如何在 jQuery UI 滑块中使用 **可折叠** **选项**。 **可折叠** **选项**允许在 jQuery UI 中取消选择选项卡。

**语法:**

```html
$( ".selector" ).tabs(
   { collapsible : true}
);
```

**参数:**不接受任何参数。

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**例 1:**

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
        $(function() {
            $("#gfg").tabs({
                collapsible: false
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs collapsible option</h3>

    <div id="gfg">
        <ul>
            <li><a href="#gfg1">Tab 1</a></li>
            <li><a href="#gfg2">Tab 2</a></li>
            <li><a href="#gfg3">Tab 3</a></li>
        </ul>

        <div id="gfg1">
            <p>
                tab Number -1
            </p>
        </div>

        <div id="gfg2">
            <p>
                tab Number -2
            </p>
        </div>

        <div id="gfg3">
            <p>
                tab Number -3
            </p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/4e5e308a00366efdb4dd215df9ec5988.png)

**例 2:**

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
        $(function() {
            $("#gfg").tabs({
                collapsible : true
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs collapsible option</h3>

    <div id="gfg">
        <ul>
            <li><a href="#gfg1">Tab 1</a></li>
            <li><a href="#gfg2">Tab 2</a></li>
            <li><a href="#gfg3">Tab 3</a></li>
        </ul>

        <div id="gfg1">
            <p>
                tab Number -1
            </p>
        </div>

        <div id="gfg2">
            <p>
                tab Number -2
            </p>
        </div>

        <div id="gfg3">
            <p>
                tab Number -3
            </p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/3337d1b7d084c088fc23d3061fd4fa3e.png)