# jQWidgets jqxWindow 动画类型属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-animation type-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-animationtype-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

*动画类型*属性用于设置或获取指定窗口的关闭和显示动画类型。如下所示，该属性有四个可能的值。

*   没有
*   “褪色”
*   幻灯片
*   “合并”

**语法:**

设置*动画类型*属性。

```html
$('#jqxWindow').jqxWindow({ animationType: 'combined' });  
```

获取*动画类型*属性:

```html
var animationType = $('#jqxWindow').jqxWindow('animationType'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

**示例:**以下示例说明了 jQWidgets 中的 jqxWindow *动画类型*属性。本例中，*动画类型*设置为“幻灯片”。

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
                autoOpen: false,
                animationType: 'slide',
                draggable: false,
                resizable: false,
                showCloseButton: false
            });
            $("#Open").click(function () {
                $("#window").jqxWindow('open');
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> GeeksforGeeks </h1>
        <h3>
            jQWidgets jqxWindow animationType Property
        </h3>
        <div id='window'>
            <div>Header</div>
            <div>GeeksforGeeks</div>
        </div>
        <input type="button" 
            value="Animate the Window" id="Open" />
    </center>
</body>

</html>
```

**输出:**

![](img/e73c8019c145c1da99f3e9446d05231f.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)