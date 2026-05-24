# jQuery 用户界面可调整大小的手柄选项

> 原文:[https://www . geeksforgeeks . org/jquery-ui-resizable-handles-option/](https://www.geeksforgeeks.org/jquery-ui-resizable-handles-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 可调整大小句柄选项用于处理用于调整大小的边缘。

它支持两种类型的值，即–

*   **字符串:**保存字符串值，即 n、e、s、w、ne、se、sw、nw、all。
*   **对象:**保存对象形式的键，即{ n、e、s、w、ne、se、sw、nw }。

**语法:**

```html
$(".selector").resizable({
   handles: "n, e, s, w"
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

    <h3>jQuery UI Resizable handles Option</h3>

    <div id="first_div">Div content</div>

    <script>
        $(function () {
            $("#first_div").resizable({
                handles: "n, e, s, w"
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/4c1a83af08c7bcf0039c46f4b9b6be3b.png)
**参考:**[https://api.jqueryui.com/resizable/#option-handles](https://api.jqueryui.com/resizable/#option-handles)