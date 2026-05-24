# jQuery 用户界面对话框关闭文本选项

> 原文:[https://www . geesforgeks . org/jquery-ui-dialog-closext-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-closetext-option/)

**关闭文本**选项用于替换关闭按钮上的默认值。默认情况下，值为“关闭”。

**语法:**

```html
$( ".selector" ).dialog({
   closeText : "close"
});
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

    <script src=
        "https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function () {
            $("#gfg").dialog({
                autoOpen: false,
                closeText: "click!"
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| closeText dialog option
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/2a7c72fa22d28133a7f5b66a145d482b.png)