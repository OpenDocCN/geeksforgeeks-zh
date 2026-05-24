# jQWidgets jqxRating enable()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxrating-enable-method/](https://www.geeksforgeeks.org/jqwidgets-jqxrating-enable-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxRating 表示一个 jQuery 小部件，显示评级选项以选择评级。此小部件用于配置 jqxRating 小部件项目的大小、图像和显示项目的数量等。

**enable()** 方法用于启用 jqxRating 小部件。它不接受任何参数，也不返回值。

**语法:**

```html
$('Selector').jqxRating('enable'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all

**示例:**以下示例说明了 jQWidgets jqxRating**enable()**方法。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxrating.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxRating enable() Method
        </h3>

        <div id='jqxRating'></div>

        <input type="button" value="Enable Widget" id="GFG"
            style="padding: 5px 10px; margin-top: 20px;">
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxRating").jqxRating({
                width: 200,
                height: 35,
                count: 10
            });

            $('#jqxRating').jqxRating('disable'); 

            $("#GFG").on('click', function() {
                $('#jqxRating').jqxRating('enable'); 
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9f036916107b2c055abf6bb6f2d5fb68.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxrating/jquery-rating-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxrating/jquery-rating-api.htm)