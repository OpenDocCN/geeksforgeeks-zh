# jquery ui progress bar 类选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui progress bar 类别选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI progressbar 类选项用于添加一些额外的类来添加小部件的元素。

**语法:**

```html
$( ".selector" ).progressbar({
  classes: {
    "ui-progressbar": "highlight"
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
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>

    <h3>jQuery UI progressbar classes option</h3>

    <div id="progressbar"></div>

    <script>
        $("#progressbar").progressbar({
            value: 57,
            classes: {
                "ui-progressbar": "highlight"
            }
        });
    </script>
</body>

</html>
```

**输出:**

![](img/dab6b817a6bfa0985acfbe24daa7856c.png)

**参考:**[https://API . jquery ui . com/progress bar/# option-classes](https://api.jqueryui.com/progressbar/#option-classes)