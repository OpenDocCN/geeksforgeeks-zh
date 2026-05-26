# jQuery UI 手风琴类选项

> 原文:[https://www . geesforgeks . org/jquery-ui-accordion-class-option/](https://www.geeksforgeeks.org/jquery-ui-accordion-classes-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI Accordion 类选项用于添加一些额外的类，以便将样式添加到元素中。

**语法:**

```html
$( ".selector" ).accordion({
  classes: {
    "ui-accordion": "highlight"
  }
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
            font-size: 22px;
        }
    </style>

    <script>
        $(function () {
            $("#gfg").accordion({
                classes: {
                    "ui-accordion": "highlight"
                }
            });
        });
    </script>
</head>

<body>
    <h1 style="color:green">GeeksforGeeks</h1>
    <h3>jQuery UI Accordion classes Option</h3>
    <br><br>

    <div id="gfg">
        <h3>GFG</h3>
        <div>GeeksforGeeks</div>
        <h3>Geeks</h3>
        <div>GeeksforGeeks</div>
        <h3>GeeksforGeeks</h3>
        <div>Welcome to GeeksforGeeks</div>
    </div>
</body>

</html>
```

**输出:**

![](img/bb6449143a805d3fae66e192f55cf2bb.png)

**参考:**T2】https://api.jqueryui.com/accordion/#option-classes