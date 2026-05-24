# jQuery 用户界面选项卡禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-tab s-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-tabs-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 选项卡小部件帮助我们将一些内容放在不同的选项卡中，并允许我们在它们之间切换。在本文中我们将看到如何在 jQuery UI 滑块中使用 **禁用** **选项**。 **禁用** **选项**用于禁用 jQuery 界面中的选项卡。

**语法:**

```html
$( ".selector" ).tabs(
   { disabled : true }
);
```

**参数:**

*   **布尔值:**如果设置为真，将禁用所有面板。
*   **数组:** 包含标签的从零开始的索引的数组

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
        $(function () {
            $("#gfg").tabs({
                disabled : true
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs disabled option</h3>

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

![](img/2dbf11bfeaa356550eb7a1d4d445d185.png)

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
        $(function () {
            $("#gfg").tabs({
                disabled: [0, 1]
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs disabled option</h3>

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

![](img/667a6614f7c3d2916113ab976ba20614.png)