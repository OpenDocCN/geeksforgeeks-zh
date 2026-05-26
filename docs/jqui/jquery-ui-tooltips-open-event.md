# jQuery 用户界面工具提示打开事件

> 原文:[https://www . geeksforgeeks . org/jquery-ui-工具提示-打开-事件/](https://www.geeksforgeeks.org/jquery-ui-tooltips-open-event/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 工具提示小部件帮助我们添加新的主题，并允许自定义。在本文中，我们将看到如何在 jQuery UI 工具提示中使用**打开**事件。当工具提示在 jQuery UI **中打开时，触发**打开**事件。**

**语法:**

```html
$(".selector").tooltip(
   open: function(event, ui) {}
);
```

**参数:**此方法不接受任何参数。

**CDN 链接:**

*   首先，添加项目所需的 jQuery UI 脚本。

> <link href="”https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="”stylesheet”">
> <脚本 src = " https://code . jquery . com/jquery-1 . 10 . 2 . js "></脚本>
> <脚本 src = " https://code . jquery . com/ui/1 . 10 . 4/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link
      href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
      rel="stylesheet"
    />
    <script src=
"https://code.jquery.com/jquery-1.10.2.js">
    </script>
    <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <h1 style="color: green">GeeksforGeeks</h1>
    <h3>jQuery UI | Tooltip open event</h3>

    <script>
      $(function () {
        $("#gfgtt").tooltip({
          track: true,
          open: function (event, ui) {
            console.log("open event is fired");
          },
        });
        $("#gfg").click(function () {
          $("#gfgtt").tooltip("enable");
        });
      });
    </script>
  </head>

  <body>
    <input id="gfg" type="submit" name="GeeksforGeeks" value="click" />
    <span id="gfgtt" title="GeeksforGeeks"> Click here!</span>
  </body>
</html>
```

**输出:**点击按钮，显示工具提示并触发打开事件，如下所示。

![](img/700bf2bac5c2f8d4220a9e029e7d2419.png)

**参考:**T2】https://api.jqueryui.com/tooltip/#event-open