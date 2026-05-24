# jQWidgets jqxWindow collapsanimationduration 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-collapsanimationduration-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-collapseanimationduration-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

*折叠动画持续时间*属性用于确定展开或折叠动画的持续时间，单位为毫秒。

**语法:**

设置*拼贴动画持续时间*属性。

```html
$('#jqxWindow').jqxWindow({ collapseAnimationDuration:500 });  
```

获取*拼贴动画持续时间*属性。

```html
var duration = $('#jqxWindow').jqxWindow('collapseAnimationDuration'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

**示例:**以下示例说明了 jQWidgets 中的 jqxWindow*collapanimationduration*属性。例如，*拼贴动画持续时间*设置为 4000。

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
            $('#jqxwindow').jqxWindow({
                showCollapseButton: true,
                collapseAnimationDuration: 4000,
                width: 200,
                height: 100
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;"> GeeksforGeeks </h1>
        <h3> 
            jQWidgets jqxWindow 
            collapseAnimationDuration Property 
        </h3>
        <div id='jqxwindow'>
            <div> Header</div>
            <div>
                <div>GeeksforGeeks</div>
            </div>
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/14e690267a42ebe5d3ad1502308a5456.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)