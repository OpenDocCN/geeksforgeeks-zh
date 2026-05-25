# 如何使用 jQuery UI 制作基础对话框？

> 原文: [https://www.geeksforgeeks.org/how-to-make-a-basic-dialog-using-jquery-ui/](https://www.geeksforgeeks.org/how-to-make-a-basic-dialog-using-jquery-ui/)

在本文中，我们将使用 `jQuery UI` 创建一个基本对话框。

**方法:** 首先，添加项目所需的 `jQuery UI` 脚本。

> ```html
> <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
> <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
> <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
> ```

## 示例 1

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
                autoOpen: true,
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        jquery UI| basic dialog option
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/844902fdf74fb359098940e650dce8b2.png)

## 示例 2

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
            });
            $("#geeks").click(function () {
                $("#gfg").dialog("open");
            });
        });
    </script>
</head>

<body>
    <div id="gfg" title="GeeksforGeeks">
        Jquery UI| basic dialog option
    </div>

    <button id="geeks">Open Dialog</button>
</body>

</html>
```

**输出:**

![](img/330fea05b2485f1005e092840077b498.png)