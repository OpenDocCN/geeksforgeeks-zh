# jQuery UI 对话框关闭()方法

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-close-method/](https://www.geeksforgeeks.org/jquery-ui-dialog-close-method/)

**close()** 方法用于禁用对话框。此方法不接受任何参数

**语法:**

```html
$( ".selector" ).dialog("close");
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
                $("#gfg").dialog("close");
            });
        });
    </script>
</head>

<body>
    <div id="gfg">
        Jquery UI| close dialog method
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/ce19b5a924f452b54717f7f42852225f.png)