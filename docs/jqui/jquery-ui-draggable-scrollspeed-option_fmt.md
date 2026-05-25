# jQuery 用户界面可拖动滚动速度选项

> 原文: [https://www.geeksforgeks.org/jquery-ui-draggable-scrollspeed-option/](https://www.geeksforgeks.org/jquery-ui-draggable-scrollspeed-option/)

jQuery 用户界面由图形用户界面小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery 用户界面可拖动 `scrollSpeed` 选项用于设置窗口滚动的速度。如果 `scroll` 选项设置为 `false`，此选项将不起作用。

**语法:**

```javascript
$( ".selector" ).draggable({
    scrollSpeed: val
});
```

**CDN 链接:** 首先，添加项目所需的 jQuery UI 脚本。

```html
<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
<script src="//code.jquery.com/jquery-1.12.4.js"></script>
<script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
```

**示例:**

### HTML

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
    <script src="//code.jquery.com/jquery-1.12.4.js"></script>
    <script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
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
    <h3>jQuery UI Draggable scrollSpeed Option</h3>
    <div id="div_element">Div content</div>
    <script>
        $(function () {
            $("#div_element").draggable({
                scroll: true,
                scrollSpeed: 100
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9224fa257fbbe97e63c3547c90a6f4c4.png)

**参考:** [https://api.jqueryui.com/draggable/#option-scrollSpeed](https://api.jqueryui.com/draggable/#option-scrollSpeed)