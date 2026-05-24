# jQWidgets jqxTooltip 刷新()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtooltip-refresh-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtooltip-refresh-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxTooltip 是一个 jQuery 小部件，用于显示弹出消息。jqxTooltip 小部件可以与任何 HTML 元素结合使用。

**刷新()**方法用于刷新工具提示小部件。它不接受任何参数，也不返回值。

**语法:**

```html
$("Selector").jqxTooltip('refresh');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js ">jqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtooltip . js "></script>

**示例:**下面的示例说明了 jQWidgets jqxTooltip**refresh()**方法。

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
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtooltip.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxTooltip refresh() Method
        </h3>
        <br><br>

        <input type="button" id="jqxBtn" 
            style="background: green;" 
            value="GeeksforGeeks" />
        <br><br>

        <input type="button" id="jqxBtn1" 
            style="padding: 5px 15px; margin-top: 30px;" 
            value="Refresh Tooltip Popup" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxBtn',).jqxButton({
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

            $('#jqxBtn1').on('click', function () {
                $('#jqxBtn').jqxTooltip('refresh');
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/cec2dc720a9ffbc9ae2676946eb7fd54.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-api.htm)