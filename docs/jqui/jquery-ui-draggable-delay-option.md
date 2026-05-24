# jQuery UI 可拖动延迟选项

> 原文:[https://www . geesforgeks . org/jquery-ui-draggable-delay-option/](https://www.geeksforgeeks.org/jquery-ui-draggable-delay-option/)

jQuery 用户界面由图形用户界面小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 可拖动*延迟*选项用于设置拖动元素的延迟时间。

**语法:**

```html
$( ".selector" ).draggable({
    delay: time
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
    <script src=
"//code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src=
"//code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>

    <style>
        h1 {
            color: green;
        }

        #div_element {
            width: 150px;
            height: 150px;
            background: green;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h3>jQuery UI Draggable delay Option</h3>

    <div id="div_element">Div content</div>

    <script>
        $(function () {
            $("#div_element").draggable({
                delay: 500
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/0c820d2874586338c049742f88ffe3cf.png)

可拖动延迟选项

**Reference:**[https://api.jqueryui.com/draggable/#option-delay](https://api.jqueryui.com/draggable/#option-delay)