# jQuery UI 滑块销毁()方法

> 原文:[https://www . geesforgeks . org/jquery-ui-slider-destroy-method/](https://www.geeksforgeeks.org/jquery-ui-slider-destroy-method/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。 jQuery UI 通过滑块小部件为我们提供了一个滑块控件。滑块帮助我们使用给定的范围获得某个值。在本文中，我们将看到如何销毁 jQuery UI 滑块。**销毁()**方法用于销毁当前滑块，使其功能无法使用。

**语法:**

```html
$( ".selector" ).slider("destroy");
```

**进场:**

*   首先，添加项目所需的 jQuery UI 脚本。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css"
        rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>

    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js">
    </script>

    <script>
        $(function() {
            $("#gfg").slider();
        });

        function geeks() {
            $("#gfg").slider("destroy");
        }
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h2>jQuery UI | slider destroy method</h2>
    <div id="gfg"></div>
    <br>
    <button onclick="geeks()">Click</button>
</body>

</html>
```

**输出:**

![](img/a283510779622d2ec0435698421c84e8.png)