# jQWidgets jqxWindow closeButtonAction 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-closebuttonaction-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-closebuttonaction-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

*closeButtonAction* 属性指定当用户单击 jqxWindow 的关闭按钮时会发生什么。

**语法:**

设置 *closeButtonAction* 属性。

```html
$('#jqxWindow').jqxWindow({ closeButtonAction: 'close'});  
```

获得 *closeButtonAction* 属性。

```html
var cBA = $('#jqxWindow').jqxWindow('closeButtonAction'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <script type = " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxcore。

**示例:**以下示例说明了 jQWidgets 中的 jqxWindow*closeButtonAction*属性。在下面的例子中，*关闭按钮动作*已经被设置为“*隐藏*”。

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
        src="scripts/jquery-1.10.2.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxwindow.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxwindow").jqxWindow({
                height: 100,
                width: 300,
                theme: 'energyblue',
                closeButtonAction: 'hide'
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> 
            GeeksforGeeks 
        </h1>

        <h3>jQWidgets jqxWindow closeButtonAction Property</h3>

        <div id='content'>
            <div id='jqxwindow'>
                <div> Header</div>
                <div>
                    <div>GeeksforGeeks</div>
                </div>
            </div>
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/3bbd0b2a3c544792d7894091f6047580.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)