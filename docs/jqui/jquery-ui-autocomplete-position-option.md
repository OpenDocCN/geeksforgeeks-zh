# jQuery UI 自动完成位置选项

> 原文:[https://www . geesforgeks . org/jquery-ui-autocomplete-position-option/](https://www.geeksforgeeks.org/jquery-ui-autocomplete-position-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 自动完成位置选项用于添加建议菜单相对于相关输入元素的位置。

**语法:**

```html
$( ".selector" ).autocomplete({
  position: { my : "right top", at: "right bottom" }
});
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 12 . 4 . js "></脚本>
> <脚本 src =//code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href=
    "//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>

    <script>
        $(function () {
            var list = [
                "One",
                "two",
                "Three",
                "Four",
            ];
            $("#gfg").autocomplete({
                source: list,
                position: { my: "right top", at: "right bottom" }
            });
        });
    </script>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>
    <h3>jQuery UI Autocomplete position Option</h3>

    <label for="gfg">Enter Text:</label>
    <input id="gfg">
</body>

</html>
```

**输出:**

![](img/7e6112320254b499e7d10a12a6ae4cb6.png)

**参考:**T2】https://api.jqueryui.com/autocomplete/#option-position