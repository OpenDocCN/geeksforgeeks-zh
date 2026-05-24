# jQWidgets jqxcolorppicker 高度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcolorppicker-height-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcolorpicker-height-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxColorPicker 小部件是一个 jQuery UI 小部件，用于创建颜色选择器。

*高度*属性用于设置或返回拾色器的高度。它接受数字或字符串类型的值，默认值为 null。

**语法:**

设置*高度*属性。

```html
$("selector").jqxColorPicker({height: 300});
```

返回*高度*属性。

```html
var height= $("selector").jqxColorPicker('height');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

**示例:**以下示例说明了 jQWidgets 中的 jqxcolorppicker*高度*属性。

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
            jQWidgets jqxColorPicker height Property
        </h3>

        <div id='jqxCP'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxCP").jqxColorPicker({ 
                width: 350, 
                height: 300
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/28ff9e16e5073fe487e99a1afebb7629.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcolorppicker/jquery-color picker-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcolorpicker/jquery-colorpicker-api.htm)