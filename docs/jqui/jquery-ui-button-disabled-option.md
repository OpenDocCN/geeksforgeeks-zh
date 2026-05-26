# jQuery 用户界面按钮禁用选项

> 原文:[https://www . geesforgeks . org/jquery-ui-button-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-button-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。如果按钮元素设置为真，则使用 jQuery UI 按钮禁用选项禁用按钮元素。

**语法:**

```html
$( ".selector" ).button({
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

    <h3>jQuery UI Button disabled option</h3>

    <button>GFG Button</button>

    <script>
        $("button").button({
            disabled: true
        });
    </script>
</body>

</html>
```

**输出:**

![](img/0e19f77760c24f64e573c1145cf4b551.png)