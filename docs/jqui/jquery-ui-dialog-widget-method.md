# jQuery UI 对话框小部件()方法

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-widget-method/](https://www.geeksforgeeks.org/jquery-ui-dialog-widget-method/)

jQuery UI 中的 dialog widget()方法返回对话框的 widget 元素。

**语法:**

```html
var a = $( ".selector" ).dialog("widget");
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
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>

    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function () {
            $("#gfg").dialog({
                autoOpen: false,
            });
            $("#geeks").click(function () {
                var a = $("#gfg").dialog("widget");
                console.log(a)
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| widget dialog method
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/846de07a7f4e50f6d64b24595b553bfe.png) ![](img/967fc6954ca1a1ed781e4fba96a288cf.png)