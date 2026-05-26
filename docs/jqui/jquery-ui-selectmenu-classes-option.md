# jquery ui select menu classes option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-select menu-classes 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 选择菜单类选项用于向选择菜单元素添加一些附加类。

**语法:**

```html
$( ".selector" ).selectmenu({
  classes: {
    "ui-selectmenu-menu": "highlight"
  }
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
    <h1>GeeksforGeeks</h1>

    <h3>jQuery UI Selectmenu classes option</h3>

    <label for="sub">Select Computer Subject:</label>

    <select name="sub" id="sub" class="GFG">
        <option value="Slower">HTML</option>
        <option value="Slow">CSS</option>
        <option value="Medium">JavaScript</option>
        <option value="Fast">Java</option>
        <option value="Faster">Python</option>
    </select>

    <script>
        $("#sub").selectmenu({
            classes: {
                "ui-selectmenu-button-closed": "ui-corner-all",
                "ui-selectmenu-button-open": "ui-corner-top",
                "ui-selectmenu-menu": "highlight"
            }
        });
    </script>
</body>

</html>
```

**输出:**

![](img/0f911feb6643b8fd9978c744ceaa4702.png)

**参考:**[https://API . jquery ui . com/select menu/# option-classes](https://api.jqueryui.com/selectmenu/#option-classes)