# jquery ui date picker show button panel option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-date picker-showbutton panel 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI Datepickers 小部件允许用户轻松直观地输入日期。在本文中，我们将看到如何在 jQuery UI Datepicker 中使用 **showButtonPanel** 选项。**显示按钮面板**选项如果设置为*真*，按钮面板将显示在 jQuery 用户界面中日期选择器的底部。

**语法:**

```html
$(".selector").datepicker(
   {showButtonPanel: true}
);
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**示例:**

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
"https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>
    <script>
      $(function () {
        $("#gfg").datepicker({ showButtonPanel: true });
      });
    </script>
  </head>

  <body>
      <h1>GeeksforGeeks</h1>
      <h3>jQuery UI | datepicker showButtonPanel option</h3>

    <p>Enter Date: <input type="text" id="gfg" /></p>
  </body>
</html>
```

**输出:**

![](img/5639c8e21bc68cb83f086480cdb1c832.png)

**参考:**[https://API . jquery ui . com/date picker/# option-show button panel](https://api.jqueryui.com/datepicker/#option-showButtonPanel)