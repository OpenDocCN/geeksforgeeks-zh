# jQuery UI 对话框 minHeight 选项

> 原文: [https://www.geeksforgeeks.org/jquery-ui-dialog-minheight-option/](https://www.geeksforgeeks.org/jquery-ui-dialog-minheight-option/)

`minHeight` 选项用于设置对话框可以设置的最小高度。默认情况下，该值为 150。

## 语法

```html
$( ".selector" ).dialog({
    minHeight : 150
});
```

## 方法

首先，添加项目所需的 jQuery UI 脚本。

> <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
> <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
> <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>

## 例 1

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
                minHeight: 300
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| minHeight dialog option
    </div>

<button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/144c299630ab51db503b5f97093cfbca.png)

## 例 2

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
                minHeight: 150
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| minHeight dialog option
    </div>

<button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/049f095d5caed3a54b878c9e639da0e4.png)