# jQuery UI 标签加载()方法

> 原文:[https://www.geeksforgeeks.org/jquery-ui-tabs-load-method/](https://www.geeksforgeeks.org/jquery-ui-tabs-load-method/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 选项卡小部件帮助我们将一些内容放在不同的选项卡中，允许我们在它们之间切换。在本文、中我们将看到如何在 jQuery UI 滑块中使用**load()方法**、。 **加载()方法** 强制重新加载 jQuery UI 中的索引选项卡 。

**语法:**

```html
$(".selector").tabs("load", index);
or
$(".selector").tabs("load", href);
```

**参数:**

*   **索引:**包含我们要打开的 tab 的索引。
*   **href:** 包含我们要打开的标签的引用。

**方法:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**示例 1:** 这个示例描述了 load(index)方法的实现。

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function() {
            $("#gfg").tabs();
            $("#gfg").tabs("load", 0);
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs load(index) method</h3>

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

![](img/347990efeee87b0a13d34e4150094bd0.png)

**示例 2:** 这个示例描述了 load(href)方法的实现。

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function() {
            $("#gfg").tabs();
            $("#gfg").tabs("load", '#gfg1');
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI tabs load(href) method</h3>

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

![](img/70c28082aa6d5937bb99fe9baad80f2b.png)

**参考:**T2】https://api.jqueryui.com/tabs/#method-load