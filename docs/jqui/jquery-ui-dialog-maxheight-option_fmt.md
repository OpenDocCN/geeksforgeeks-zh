# jQuery UI 对话框 maxHeight 选项

> 原文：[https://www.geeksforgeeks.org/jquery-ui-dialog-maxheight-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-maxheight-option/)

`maxHeight` 选项用于设置对话框可以设置的最大高度。默认情况下，值为 `false`。

**语法：**

```javascript
$( ".selector" ).dialog({
    maxHeight : 10
});
```

**方法：** 首先，添加项目所需的 jQuery UI 脚本。

```html
<link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
<script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
```

### 示例 1

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
    <script>
        $(function () {
            $("#gfg").dialog({
                autoOpen: false,
                maxHeight: false
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出：**

![](img/741fd3fcbb3bfbb0415cb8e5986cd358.png)

### 示例 2

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
    <script>
        $(function () {
            $("#gfg").dialog({
                autoOpen: false,
                maxHeight: 10
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
        Jquery UI| maxHeight dialog option
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出：**

![](img/b27fff3cf6ce967b18f793dd19dd9fac.png)