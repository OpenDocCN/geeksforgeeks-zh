# jquery ui select menu icons option

> 哎哎哎::1230【https://www . geeksforgeeks . org/jquery-ui-select menu-icons 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery 用户界面选择菜单图标选项用于添加带有选择菜单的图标。

**语法:**

```html
$( ".selector" ).selectmenu({
  icons: { button: "ui-icon-circle-triangle-s" }
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
    <link rel="stylesheet" href=
    "//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
    <script src="//code.jquery.com/jquery-1.12.4.js"></script>
    <script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <style>
        label {
            display: block;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>

    <h3>jQuery UI Selectmenu icons option</h3>

    <label for="sub">Select Computer Subject:</label>

    <select name="sub" id="sub">
        <option value="Slower">HTML</option>
        <option value="Slow">CSS</option>
        <option value="Medium">JavaScript</option>
        <option value="Fast">Java</option>
        <option value="Faster">Python</option>
    </select>

    <script>
        $("#sub").selectmenu({
            icons: { button: "ui-icon-circle-triangle-s" }
        });
    </script>
</body>

</html>
```

**输出:**

![](img/54d8e8f258ebd813d7d6501d54804cbd.png)

**参考:**[https://API . jquery ui . com/select menu/# option-icons](https://api.jqueryui.com/selectmenu/#option-icons)