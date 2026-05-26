# jQuery 用户界面选项卡显示选项

> 原文:[https://www.geeksforgeeks.org/jquery-ui-tabs-show-option/](https://www.geeksforgeeks.org/jquery-ui-tabs-show-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery 用户界面选项卡显示选项用于显示面板动画。它接受不同类型的值，即布尔值、数字、字符串或对象。

**语法:**

```html
$( ".selector" ).tabs({
  show: { effect: "blind", duration: 800 }
});
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 12 . 4 . js "></脚本>
> <脚本 src =//code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href=
    "//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>

    <style>
        .highlight {
            background: green;
        }
    </style>

    <script>
        $(function () {
            $("#gfg").tabs({
                show: { effect: "blind", duration: 800 }
            });
        });
    </script>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>
    <h3>jQuery UI tabs show option</h3>

    <div id="gfg">
        <ul>
            <li><a href="#gfg1">Tab 1</a></li>
            <li><a href="#gfg2">Tab 2</a></li>
            <li><a href="#gfg3">Tab 3</a></li>
        </ul>
        <div id="gfg1">
            <p>Welcome to GeeksforGeeks</p>
        </div>

        <div id="gfg2">

<p>GeeksforGeeks</p>

        </div>

        <div id="gfg3">
            <p>Welcome Geeks!</p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/81e838268754112d3fdca266ee163376.png)

**参考:**T2】https://api.jqueryui.com/tabs/#option-show