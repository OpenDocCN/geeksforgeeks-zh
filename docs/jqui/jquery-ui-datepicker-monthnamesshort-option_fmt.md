# jQuery UI DatePicker monthNamesShort 选项

> 哎哎哎: [https://www.geeksforgeeks.org/jquery-ui-datepicker-monthnameshort-option/](https://www.geeksforgeeks.org/jquery-ui-datepicker-monthnameshort-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI datepicker 的 `monthNamesShort` 选项用于设置缩写月份名称列表。它用在每个日期选择器的月标题中。其默认值为 `["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]`。

## 语法

```html
$( ".selector" ).datepicker({
  monthNamesShort: [ "Jan", "Feb", ... , "Nov", "Dec" ]
});
```

## CDN 链接

首先，添加项目所需的 jQuery UI 脚本。

```html
<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
<script src="//code.jquery.com/jquery-1.12.4.js"></script>
<script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
```

## 示例

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <link href="https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
    <script src="https://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>

    <script>
        $(function () {
            $("#gfg").datepicker({
                dateFormat: "M",
                monthNamesShort: ["Jan", "Feb", "Mar", "Apr", "Maj", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
            });
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI Datepicker monthNamesShort Option</h3>

    <div>Enter Date: <input type="text" id="gfg" /></div>
</body>

</html>
```

## 输出

![](img/67dd76eb5890efc0e1b4a903e9b73d1e.png)

`monthNamesShort` 选项

## 参考资料

[https://api.jqueryui.com/datepicker/#option-monthNamesShort](https://api.jqueryui.com/datepicker/#option-monthNamesShort)