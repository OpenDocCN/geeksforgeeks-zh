# jQWidgets jqxCalendar columnheaderlight 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcalendar-columnheaderheight-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcalendar-columnheaderheight-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxCalendar 代表一个 jQuery 日历小部件，使用户能够使用可视的月历显示来选择日期。

*列标题高度*属性用于设置或返回日历列标题的高度。列标题用于显示日历日名称。它接受数字类型值，默认值为 20。

**语法:**

```html
$('.selector').jqxCalendar({
    columnHeaderHeight: Number
});
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery-1 . 11 . 1 . min . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> 脚本类型=“text/JavaScript”src =“jqwidgets/jqxdatetimetime”

**示例:**下面的示例说明了 jQWidgets 中的 jqxCalendar*columnheaderlight*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdatetimeinput.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcalendar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/globalization/globalize.js"></script>
    <script tyle="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxCalendar columnHeaderHeight Property
        </h3>

        <div id='jqxcal'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxcal").jqxCalendar({
                theme: 'energyblue',
                width: '400px',
                height: '300px',
                columnHeaderHeight: 80
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/72e2d2526b19f5b37c7cf72a4e383fb4.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-api.htm)