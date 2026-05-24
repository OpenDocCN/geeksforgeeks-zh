# jQWidgets jqxcolorppicker 宽度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcolorppicker-width-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcolorpicker-width-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxColorPicker 小部件是一个 jQuery UI 小部件，用于创建颜色选择器。

width 属性用于设置或返回颜色选择器的宽度。它接受数字/字符串类型的值，默认值为空。

**语法:**

设置 width 属性。

```html
$("selector").jqxColorPicker({ width: 300 });
```

返回 width 属性。

```html
var width = $("selector").jqxColorPicker('width');
```

**链接文件:**从 https://www.jqwidgets.com/download/链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

以下示例说明了 jQWidgets 中的 jqxColorPicker 宽度属性:

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcolorpicker.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxColorPicker width Property
        </h3>

        <div id='jqxCP'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxCP").jqxColorPicker({ 
                width: 450, 
                height: 300
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/0af862d8d4a59e3275c91399053c466b.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcolorppicker/jquery-color picker-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcolorpicker/jquery-colorpicker-api.htm)