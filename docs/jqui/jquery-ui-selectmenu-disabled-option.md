# jquery ui select menu disabled option

> 原文:[https://www . geesforgeks . org/jquery-ui-select menu-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-selectmenu-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。如果选择菜单设置为真，jQuery UI 选择菜单禁用选项用于禁用选择菜单。

**语法:**

```html
$( ".selector" ).selectmenu({
  disabled: true
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

    <h3>jQuery UI Selectmenu disabled option</h3>

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
            disabled: true
        });
    </script>
</body>

</html>
```

**输出:**

![](img/f9476a6efc94fd80062de2155447ff42.png)

**参考:**T2】https://api.jqueryui.com/selectmenu/#option-disabled