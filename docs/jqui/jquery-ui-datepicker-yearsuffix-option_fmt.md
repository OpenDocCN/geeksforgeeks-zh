# jQuery UI Datepicker yearSuffix 选项

> 原文：[https://www.geeksforgeeks.org/jquery-ui-datepicker-yearsuffix-option/](https://www.geeksforgeeks.org/jquery-ui-datepicker-yearsuffix-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI Datepicker 小部件允许用户轻松直观地输入日期。在本文中，我们将看到如何在 jQuery UI Datepicker 中使用 `yearSuffix` 选项。`yearSuffix` 选项用于在 jQuery UI Datepicker 中添加一些年后的文字。

## 语法

```javascript
$(".selector").datepicker(
   {yearSuffix: '2021'}
);
```

## 方法

首先，添加项目所需的 jQuery UI 脚本。

```html
<link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
<script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
```

## 示例

### HTML

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet">
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
    <script>
        $(function () {
            $("#gfg").datepicker(
                { yearSuffix: "2021" }
            );
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI | datepicker yearSuffix option</h3>
    <p>Enter Date: <input type="text" id="gfg"></p>
</body>

</html>
```

## 输出

![](img/5c52412460ae98017640d1a0b50b1040.png)

## 参考

[https://api.jqueryui.com/category/widgets/](https://api.jqueryui.com/category/widgets/)