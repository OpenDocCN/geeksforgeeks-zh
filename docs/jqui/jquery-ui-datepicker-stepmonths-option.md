# jquery ui date picker step months 选项

> 原文:[https://www . geesforgeks . org/jquery-ui-date picker-step months-option/](https://www.geeksforgeeks.org/jquery-ui-datepicker-stepmonths-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 日期选择器小部件允许用户轻松直观地输入日期。在本文中，我们将看到如何在 jQuery UI Datepicker 中使用 **stepMonths** 选项。 **step months**选项  指定在 jQuery UI datepicker 中点击其中一个月份导航控件时要移动多少个月。

**语法:**

```html
$(".selector").datepicker(
   {
   showWeeks: true,
   stepMonths: 3
   }
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

    <script>
        $(function () {
            $("#gfg").datepicker(
                {
                    showWeek: true,
                    stepMonths: 3
                }
            );
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI | datepicker stepMonths option</h3>

    <p>Enter Date: <input type="text" id="gfg"></p>
</body>

</html>
```

**输出:**

![](img/8b6b42672b12fdbc650afa62b699ee16.png)

**参考:**T2】https://api.jqueryui.com/category/widgets/