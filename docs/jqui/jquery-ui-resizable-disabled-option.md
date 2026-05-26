# jQuery UI 可调整大小禁用选项

> 原文:[https://www . geeksforgeeks . org/jquery-ui-resizable-disabled-option/](https://www.geeksforgeeks.org/jquery-ui-resizable-disabled-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。如果设置为真，jQuery UI 可调整大小禁用选项用于禁用可调整大小属性。

**语法:**

```html
$(".selector").resizable({
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

        #box {
            width: 500px;
            height: 250px;
            border: 2px solid orange;
            float: left
        }

        #first_div {
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

    <h3>jQuery UI Resizable disabled Option</h3>
    <div id="first_div">Div content</div>

    <script>
        $(function () {
            $("#first_div").resizable({
                disabled: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/6f976fe5022ac7c2efd9b0f0f7a4b8ff.png)
**参考:**[https://api.jqueryui.com/resizable/#option-disabled](https://api.jqueryui.com/resizable/#option-disabled)