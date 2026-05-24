# jQWidgets jqxWindow 可拖动属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-draggable-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-draggable-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

*可拖动*属性用于设置或获取窗口是否可拖动。

**语法:**

设置*可拖动*属性。

```html
$('#jqxWindow').jqxWindow({ draggable: false});  
```

获取*可拖动*属性:

```html
var draggable = $('#jqxWindow').jqxWindow('draggable'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

**示例:**以下示例说明了 jQWidgets 中的 jqxWindow *可拖动*属性。对于本例，可拖动设置为*真*。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.summer.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.10.2.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxwindow.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#window").jqxWindow({
                position: { x: 120, y: 180 },
                autoOpen: true,
                draggable: true,
                resizable: false,
                showCloseButton: false
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> GeeksforGeeks </h1>
        <h3>
            jQWidgets jqxWindow draggable Property
        </h3>
        <div id='window'>
            <div>Header</div>
            <div>GeeksforGeeks</div>
        </div>
        <input type="button" 
            value="Below window is draggable" />
    </center>
</body>

</html>
```

**输出:**

![](img/9c625f3029d5319a62bc7f766da8a8b2.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)