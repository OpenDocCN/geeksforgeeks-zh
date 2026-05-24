# jQWidgets jqxBarGauge drawind 事件

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbargage-drawind-event/](https://www.geeksforgeeks.org/jqwidgets-jqxbargauge-drawend-event/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxBarGauge 表示一个 jQuery 条形图小部件，它为给定的值绘制一个条形图。

当 BarGauge 完成渲染时，触发**绘制结束**事件。该事件通常与 **drawStart** 事件结合使用。

**语法:**

```html
$('selector').bind('drawEnd', function () { 
    // Code
}); 
```

**链接文件:**从链接下载 [**jQWidgets**](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxdraw . js

**示例:**以下示例说明了 jQWidgets jqxbargage**drawind**事件。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdraw.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbargauge.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxBarGauge drawEnd Event
        </h3>

        <div id="gfg"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#gfg').jqxBarGauge({
                values: [100, 150, 200],
                max: 200,
                width: 300
            }).bind('drawEnd',
                function () {
                    alert('Welcome to GeeksforGeeks');
                });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/cc84fd2b48250f41d833e5c6a44f5cd3.png)

**参考:**[https://](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbargauge/jquery-bar-gauge-api.htm)[www](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbargauge/jquery-bar-gauge-api.htm)[. jqwidgets . com/jquery-widgets-documentation/documentation/jqxbargage/jquery-bar-gauge-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbargauge/jquery-bar-gauge-api.htm)