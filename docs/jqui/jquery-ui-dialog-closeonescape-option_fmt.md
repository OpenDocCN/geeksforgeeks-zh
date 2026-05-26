# jQuery UI 对话框 closeOnEscape 选项

> 原文：[https://www.geeksforgeeks.org/jquery-ui-dialog-closeonescape-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-closeonescape-option/)

`closeOnEscape` 选项如果设置为 `true`，当对话框获得焦点时，按下退出键（Esc）将关闭对话框。默认情况下，值为 `true`。

## 语法

```html
$( ".selector" ).dialog({
    closeOnEscape : true
});
```

## 方法

首先，添加项目所需的 jQuery UI 脚本。

```html
<link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
<script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
```

## 例 1

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
                closeOnEscape: true,
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| closeOnEscape dialog option
    </div>
    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出：**

![](img/4a4ed4be537f510df0cde442acef9226.png)

## 例 2

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
                closeOnEscape: false,
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| closeOnEscape dialog option
    </div>
    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出：**

![](img/5783f0c23ca0a6b3eb52ec071c20eba6.png)