# jQWidgets jqxCalendar restricted data 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxcalendar-restricted ddates-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcalendar-restricteddates-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxCalendar 代表一个 jQuery 日历小部件，使用户能够使用可视的月历显示来选择日期。

*限制日期*属性用于设置或返回日历的限制日期。受限日期不可点击。它接受数组类型值，默认值为[]。

**语法:**

```html
$('.selector').jqxCalendar({
  restrictedDates: Array
});
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

**示例:**下面的示例说明了 jQWidgets 中的 jqxCalendar*restricted dates*属性。

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
        src="jqwidgets/globalization/globalize.js">
    </script>
    <script tyle="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
</head>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxCalendar restrictedDates Property
        </h3>

        <div id='jqxcal'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var restrictedDates = new Array();
            var date1 = new Date();
            date1.setHours(0,0,0);
            date1.setDate(12);

            var date2 = new Date();
            date2.setHours(0,0,0);
            date2.setDate(16);

            var date3 = new Date();
            date3.setHours(0,0,0);
            date3.setDate(18);

            restrictedDates.push(date1);
            restrictedDates.push(date2);
            restrictedDates.push(date3);

            $("#jqxcal").jqxCalendar({
                width: '400px',
                height: '300px',
                restrictedDates: restrictedDates
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/ffc2995e81eb0a36e6fc80c9c26f4c58.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-api.htm)