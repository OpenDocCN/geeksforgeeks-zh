# jQuery 用户界面标签激活选项

> 原文:[https://www.geeksforgeeks.org/jquery-ui-tabs-active-option/](https://www.geeksforgeeks.org/jquery-ui-tabs-active-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 选项卡小部件帮助我们将一些内容放在不同的选项卡中，并允许我们在它们之间切换。在本文中我们将看到如何在 jQuery UI 滑块中使用 **激活** **选项**。 **激活** **选项**指定 jQuery UI 选项卡中当前激活的选项卡。默认情况下，值为 **0。**

**语法:**

```html
$( ".selector" ).tabs(
   { active: 1 }
);
```

**参数:**

*   **布尔值:**如果设置为 false 将折叠所有面板。如果设置为 true，第 0 个索引标签将被激活。
*   **编号:** 活动面板的从零开始的索引。

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
                active: 2
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs active option</h3>

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

![](img/52101ebea6b5a0a32c3249287509942b.png)

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
                active: false
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs active option</h3>

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

![](img/abf7bc4a192e9e7ce08e5101123d02df.png)