# jquery ui dragable cursor at 选项

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-draggable-cursor at 选项/

jQuery 用户界面由图形用户界面小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 可拖动光标选项用于设置拖动辅助对象相对于鼠标光标的偏移量。坐标是一个或两个键的组合:{上、左、右、下}。

**语法:**

```html
$( ".selector" ).draggable({
    cursorAt: { left: 5 }
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

    <h3>jQuery UI Draggable cursorAt Option</h3>

    <div id="div_element">Div content</div>

    <script>
        $(function () {
            $("#div_element").draggable({
                cursorAt: { left: 25 }
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/b284033e6c5ad03d74f849ebb01e9adb.png)
**参考:**[https://API . jquery ui . com/draggable/# option-cursor at](https://api.jqueryui.com/draggable/#option-cursorAt)