# jqwidgets jqxcolrpkers get color()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcolorppicker-getcolor-method/](https://www.geeksforgeeks.org/jqwidgets-jqxcolorpicker-getcolor-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxColorPicker 小部件是一个 jQuery UI 小部件，用于创建颜色选择器。

getColor()方法用于返回十六进制或 rgb 格式的颜色。它不接受任何参数，并以十六进制格式返回颜色对象。我们使用 object.hex 表示十六进制代码，object.r、object.g、object.b 表示 rgb 颜色值。

**语法:**

```html
$("selector").jqxColorPicker('getColor');
```

**链接文件:**从 https://www.jqwidgets.com/download/链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

以下示例说明了 jQWidgets 中的 jqxColorPicker getColor()方法:

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
            jQWidgets jqxColorPicker getColor() Method
        </h3>

        <div id='jqxCP'></div>
        <br>
        <input type="button" id='jqxBtn' 
            style="padding: 5px 20px" value="Get color" />
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxCP").jqxColorPicker({ 
                width: 450, 
                height: 300
            });

            $('#jqxBtn').on('click', function () {
                var color = $("#jqxCP")
                    .jqxColorPicker('getColor');

                var hex = color.hex;

                var rgb = "(" + color.r + "," 
                    + color.g + "," + color.b + ")"; 

                alert("Hex Color: #" + hex 
                    + ", RGB Value: " + rgb);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/40bda6969eae912cfa4e87ceee4e811c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcolorppicker/jquery-color picker-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcolorpicker/jquery-colorpicker-api.htm)