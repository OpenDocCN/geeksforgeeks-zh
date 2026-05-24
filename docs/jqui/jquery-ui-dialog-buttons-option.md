# jQuery 用户界面对话框按钮选项

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-buttons-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-buttons-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。“jQuery 用户界面对话框按钮”选项用于指定应在对话框中显示的按钮。

**语法:**

```html
$( ".selector" ).dialog({
  buttons: [
    {
      text: "Ok",
      icon: "ui-icon-heart",
      click: function() {
        $( this ).dialog( "close" );
      }
    }
  ]
});
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 12 . 4 . js "></脚本>
> <脚本 src =//code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

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

    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>

    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function () {
            $("#gfg").dialog({
                autoOpen: false,
                buttons: [
                    {
                        text: "Ok",
                        click: function () {
                            $(this).dialog("close");
                        }
                    }
                ]
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body style="text-align: center;">
    <h1 style="color:green;">GeeksforGeeks</h1>
    <h3>jQuery UI Dialog buttons Option</h3>

    <button id="geeks">Open Dialog</button>

    <div id="gfg" title="GeeksforGeeks">
        Welcome to GeeksforGeeks
    </div>
</body>

</html>
```

**输出:**

![](img/0890e4dfae10e9fa3388acad61e13b96.png)

**参考:**T2】https://api.jqueryui.com/dialog/#option-buttons