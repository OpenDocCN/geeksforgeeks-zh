# jQWidgets jqxWindow bringToFront()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-bringtofront-method/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-bringtofront-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxWindow 用于在应用程序中输入数据或查看信息。

**bringToFront()** 方法用于将指定的窗口带到前面。

**语法:**

```html
$('selector').jqxWindow('bringToFront');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

**示例:**下面的示例说明了 jQWidgets **bringToFront()** 方法属性。

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
                width: 200,
                height: 100
            });
            $('#jqxwindow2').jqxWindow({
                autoOpen: false,
                height: 100,
                isModal: true,
                width: 200
            });
            $("#jqxbutton").jqxButton({
                height: 30
            });
            $('#jqxbutton').click(function () {
                $("#jqxwindow2").jqxWindow('open');
                $("#jqxwindow2").jqxWindow('bringToFront');
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> GeeksforGeeks </h1>
        <h3> jQWidgets jqxWindow bringToFront() Method </h3>
        <input type="button" id="jqxbutton" 
            value="Invoke the bringToFront method" />
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
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/7855ef0c650943e865440e5aa1ed8ce3.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)