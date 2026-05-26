# jQuery UI 进度条禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-progress bar-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-progressbar-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI progressbar disabled 选项用于禁用设置为 true 的 progressbar。

**语法:**

```html
$( ".selector" ).progressbar({
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
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>

    <h3>jQuery UI progressbar disabled option</h3>

    <div id="GFG"></div>

    <script>
        $("#GFG").progressbar({
            disabled: true,
            value: 25
        });
    </script>
</body>

</html>
```

**输出:**

![](img/1cbf280ab5a1504d870714d2b1b86418.png)

**参考:**T2】https://api.jqueryui.com/progressbar/#option-disabled