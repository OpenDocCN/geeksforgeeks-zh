# jquery ui date picker numerofmonths 选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-date picker-numerofmonths 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jquery yui 中的 jQueryUI Datepickers 小部件允许用户轻松直观地输入日期。在本文中，我们将看到如何在 jQuery UI 日期选择器中使用 **numberOfMonths 选项**。**月数选项**指定要在 jQuery 用户界面日期选择器中显示的月数。

**语法:**

```html
$(".selector").datepicker(
   {numberOfMonths: 2}
);
```

**CDN 链接:** >首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
      rel="stylesheet"/>
    <script src=
"https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>

    <!-- Javascript -->
    <script>
      $(function () {
        $("#gfg").datepicker({ dateFormat: "yy/dd/mm", numberOfMonths: 2 });
      });
    </script>
  </head>
  <h1>GeeksforGeeks</h1>
  <h3>jQuery UI | datepicker numberOfMonths option</h3>

  <body>
    <!-- HTML -->

    <p>Enter Date: <input type="text" id="gfg" /></p>
  </body>
</html>
```

**输出:**

![](img/4ea771fa0eae900d9e85bd775f42456c.png)

**参考:**[https://API . jquery ui . com/date picker/# option-numerofmonths](https://api.jqueryui.com/datepicker/#option-numberOfMonths)