# jQuery UI Datepicker nextText 选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-date picker-nexttext 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQueryUI 中的 jQueryUI Datepickers 小部件允许用户轻松直观地输入日期。在本文中，我们将看到如何在 jQuery UI Datepicker 中使用 **nextText 选项** 。 **Next text 选项** 指定在 jQuery UI 日期选择器中替换下个月的 Next 默认标题的文本。

**语法:**

```html
$(".selector").datepicker(
   {nextText: 'click'}
);
```

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

    <!-- JavaScript code -->
    <script>
        $(function () {
            $("#gfg").datepicker(
                {
                    dateFormat: "yy/dd/mm",
                    nextText: 'click'
                }
            );
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI | datepicker nextText option</h3>

    <p>Enter Date: <input type="text" id="gfg"></p>
</body>

</html>
```

**输出:**

![](img/8f5f21b19b64194784ac32ecf2f07890.png)

**参考:**T2】https://api.jqueryui.com/category/widgets/