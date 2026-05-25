# jQuery UI 可调整距离选项

> 原文：`https://www.geeksforgeeks.org/jquery-ui-resizable-distance-option/`

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery UI 非常适合为网页构建用户界面。jQuery UI 的 `resizable` 的 `distance` 选项用于在设置为 `true` 时禁用可调整大小的属性。

### 语法

```javascript
$(".selector").resizable({
   disabled: true
});
```

### CDN 链接

首先，添加项目所需的 jQuery UI 脚本。

> `<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">`
> `<script src="//code.jquery.com/jquery-1.12.4.js"></script>`
> `<script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>`

### 示例

#### HTML

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

    <h3>jQuery UI Resizable distance Option</h3>

    <div id="first_div">Div content</div>

    <script>
        $(function () {
            $("#first_div").resizable({
                distance: 40
            });
        });
    </script>
</body>

</html>
```

### 输出

![](img/1584590620ea6773f1bffd9c1c243d20.png)

### 参考

`https://api.jqueryui.com/resizable/#option-distance`