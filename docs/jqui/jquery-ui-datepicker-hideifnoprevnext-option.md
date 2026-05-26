# jquery ui date picker hideifnorev next option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-date picker-hideifnorev next 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。如果设置了 minDate 和 maxDate 选项，jQuery UI Datepicker hideifnorevnext 选项用于隐藏上一个和下一个选项。

**语法:**

```html
$( ".selector" ).datepicker({
  hideIfNoPrevNext: true
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
    <meta charset="utf-8" />
    <link href=
    "https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" 
        rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <!-- Javascript -->
    <script>
        $(function () {
            $("#gfg").datepicker({
                minDate: new Date(2021, 1 - 1, 1),
                maxDate: "+1m",
                hideIfNoPrevNext: true
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI Datepicker hideIfNoPrevNext Option</h3>

    <div>Enter Date: <input type="text" id="gfg" /></div>
</body>

</html>
```

**输出:**

![](img/c3f1db787f2d8d6b0ad50f7a58bf5b2a.png)

**参考:**[https://API . jquery ui . com/date picker/# option-hideifnorev next](https://api.jqueryui.com/datepicker/#option-hideIfNoPrevNext)