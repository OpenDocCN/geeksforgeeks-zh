# jQWidgets jqxWindow closeAll()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-close all-method/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-closeall-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxWindow 用于在应用程序中输入数据或查看信息。

**closeAll()** 方法用于关闭所有当前打开的非模态窗口。此方法不接受任何参数。

**语法:**

```html
$('selector').jqxWindow('closeAll');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

下面的例子说明了 jQWidgets **closeAll()** 方法。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
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
                position: 'left',
                width: 150,
                height: 100
            });
            $('#jqxwindow2').jqxWindow({
                height: 100,
                width: 100
            });
            $('#jqxwindow3').jqxWindow({
                position: 'right',
                height: 100,
                width: 100
            });
            $("#jqxbutton").jqxButton({
                height: 30
            });
            $('#jqxbutton').click(function () {
                $("#jqxwindow").jqxWindow('closeAll');
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> GeeksforGeeks </h1>
        <h3> jQWidgets jqxWindow closeAll() Method </h3>
        <input type="button" id="jqxbutton" 
            value="Invoke the closeAll() method" />
        <div id='content'>
            <div id='jqxwindow'>
                <div> Header</div>
                <div>
                    <div>GeeksforGeeks</div>
                </div>
            </div>
            <div id='jqxwindow2'>
                <div> Header2</div>
                <div>
                    <div>GFG</div>
                </div>
            </div>
            <div id='jqxwindow3'>
                <div> Header3</div>
                <div>
                    <div>CSE</div>
                </div>
            </div>
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/8d46b0c7f9afb526a0b69a07b07be1ff.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)