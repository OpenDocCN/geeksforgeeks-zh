# jqwidgets jqxcolrproprick set color()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcolorppicker-set color-method/](https://www.geeksforgeeks.org/jqwidgets-jqxcolorpicker-setcolor-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxColorPicker 小部件是一个 jQuery UI 小部件，用于创建颜色选择器。

setColor()方法用于以十六进制或 rgb 格式设置颜色。它接受包含十六进制或 rgb 格式颜色代码的对象/字符串类型的单个参数。它不返回值。

**语法:**

```html
$("selector").jqxColorPicker('setColor');
```

**链接文件:**从 https://www.jqwidgets.com/download/链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

以下示例说明了 jQWidgets 中的 jqxColorPicker setColor()方法:

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
            jQWidgets jqxColorPicker setColor() Method
        </h3>

        <div id='jqxCP'></div>
        <br>
        <input type="button" id='jqxBtn' 
            style="padding: 5px 20px" value="Set color" />
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxCP").jqxColorPicker({ 
                width: 450, 
                height: 300
            });

            $('#jqxBtn').on('click', function () {
                var color = $("#jqxCP")
                    .jqxColorPicker('setColor', '#308D46');
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/c2c6a89988bb8f95d44cb4bff2a48924.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcolorppicker/jquery-color picker-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcolorpicker/jquery-colorpicker-api.htm)