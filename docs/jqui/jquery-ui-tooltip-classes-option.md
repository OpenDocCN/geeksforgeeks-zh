# jquery ui tooltip classes option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-tooltip-classes 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 工具提示类选项用于添加一些额外的类，以向工具提示元素添加样式。

**语法:**

```html
$( ".selector" ).tooltip({
  classes: {
    "ui-tooltip": "highlight"
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
            border: 1px solid #eee;
            background: green;
            color: white;
            padding: 5px 10px;
        }
    </style>
    <script>
        $(document).ready(function () {
            $("#p1").tooltip({
                classes: {
                    "ui-tooltip": "highlight"
                }
            });
        });
    </script>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>
    <h2>jQuery UI Tooltip classes option</h2>

    <p id="p1">
        <a href="#" title="This is a tooltip">Tooltips</a>
        GeeksforGeeks is a computer science portal
    </p>

</body>

</html>
```

**输出:**

![](img/59a378810ecfd7823a49c03fb65698a9.png)

**参考:**[https://API . jquery ui . com/tooltip/# option-classes](https://api.jqueryui.com/tooltip/#option-classes)