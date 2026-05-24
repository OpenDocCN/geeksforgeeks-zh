# jQWidgets jqxCalendar 启用悬停属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcalendar-enable hover-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcalendar-enablehover-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxCalendar 代表一个 jQuery 日历小部件，使用户能够使用可视的月历显示来选择日期。

**启用悬停属性**用于设置或返回一个指示悬停状态是否启用的值。当鼠标光标在日历单元格上移动时，显示悬停状态。它接受布尔类型值，默认值为真。

**语法:**

```html
$('.selector').jqxCalendar({
   enableHover: Boolean
});
```

**链接文件:**从 https://www.jqwidgets.com/download/链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery-1 . 11 . 1 . min . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> 脚本类型=“text/JavaScript”src =“jqwidgets/jqxdatetimetime”

以下示例说明了 jQWidgets 中的 jqxCalendar enableHover 属性:

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
"jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
            src=
"scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdatetimeinput.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcalendar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/globalization/globalize.js">
    </script>
    <script tyle="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxCalendar enableHover Property
        </h3>

        <div id='jqxcal'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxcal").jqxCalendar({
                width: '400px',
                height: '300px',
                enableHover: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/2f95ce400c16c264ddeef3a87c698ebf.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-api.htm)