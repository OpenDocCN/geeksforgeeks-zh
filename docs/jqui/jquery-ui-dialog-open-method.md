# jQuery UI 对话框打开()方法

> 原文:[https://www.geeksforgeeks.org/jquery-ui-dialog-open-method/](https://www.geeksforgeeks.org/jquery-ui-dialog-open-method/)

**打开(**)方法用于打开对话框。此方法不接受任何参数

**语法:**

```html
$( ".selector" ).dialog("open");
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
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| open dialog method
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/65c23a03a5702b88a7e2902c720730f4.png)