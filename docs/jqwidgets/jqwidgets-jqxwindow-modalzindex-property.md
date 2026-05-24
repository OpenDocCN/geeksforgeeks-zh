# jQWidgets jqxWindow 模态指数性质

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-modalzindex-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-modalzindex-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

***模态索引*** 属性用于在显示为模态对话框时设置或获取指定的 jqxWindow 的 z 索引。

**语法:**

用于设置**属性。**

```html
$('#jqxWindow').jqxWindow({ modalZIndex: 99999}); 
```

**获取**属性。****

```html
**var modalZIndex = $('#jqxWindow').jqxWindow('modalZIndex');** 
```

******链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。****

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> ****< link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "****

******示例:**下面的示例说明了 jQWidgets 中的 jqxWindow***modalZIndex*****属性。在下面的例子中，***modalZIndex*****已经设置为 9999。********

## ******超文本标记语言******

```html
****<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css" />
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.summer.css" 
          type="text/css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.10.2.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxwindow.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxwindow").jqxWindow({
                height: 100,
                width: 300,
                theme: 'energyblue',
                isModal: true,
                modalZIndex: 9999
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;"> 
          GeeksforGeeks 
        </h1>
        <h3> 
          jQWidgets jqxWindow modalZIndex Property 
        </h3>
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

</html>****
```

********输出:********

****![](img/d7f28d890b52dbc429c0d31ea8399d77.png)****

******参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)****