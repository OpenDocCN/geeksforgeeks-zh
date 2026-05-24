# jQWidgets jqxTooltip 宽度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtooltip-width-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtooltip-width-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxTooltip 是一个 jQuery 小部件，用于显示弹出消息。jqxTooltip 小部件可以与任何 HTML 元素结合使用。

**宽度属性**用于设置或返回 jqxTooltip 小部件的宽度。它接受数字/字符串类型的值，默认值为“自动”。

**语法:**

设置 width 属性。

```html
$('Selector').jqxTooltip({ width: Number/String });
```

返回 width 属性。

```html
var width = $('Selector').jqxTooltip('width');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "【T15jqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtooltip . js "></script>

下面的例子说明了 jQWidgets jqxTooltip 宽度属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css">
    <script type="text/javascript"
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript"
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript"
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript"
        src=".jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript"
        src="jqwidgets/jqxtooltip.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxTooltip width Property
        </h3>
        <br><br>

        <input type="button" id="jqxBtn"
            style="background: green;"
            value="GeeksforGeeks" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxBtn').jqxButton({
                width: 150,
                height: 50
            });

            $("#jqxBtn").jqxTooltip({
                theme: 'energyblue',
                content: 'A computer science portal',
                position: 'top',
                width: 250,
                height: 30
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/e226fa6b892335ba28a59404501dffa6.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-api.htm)