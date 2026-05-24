# jQWidgets jqxTimePicker footerTemplate 属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxtimepicker-footertemplate-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtimepicker-footertemplate-property/)

**简介:jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTimePicker** 代表一个 jQuery 小部件，用于选择小时和分钟格式的时间。

*页脚模板*属性用于设置或返回页脚模板。 *footerTemplate* 属性的值可以是 HTMLTemplateElement 的 id，也可以是 HTMLTemplateElement 本身的 id。它接受 String/HTMLTemplateElement 类型值。

**语法:**

设置 *footerTemplate* 属性。

```html
$('selector').jqxTimePicker({ footerTemplate: String });
```

返回 *footerTemplate* 属性。

```html
var footerTemplate = $('selector').jqxTimePicker('footerTemplate');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> 脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore。

**示例:**以下示例说明了 jQWidgets jqxTimePicker*footerTemplate*属性。

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
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdraw.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtimepicker.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxTimePicker footerTemplate Property
        </h3>

        <div id="jqxTP"></div>

        <template id="TempBtn">
            <input type="button" value="GeeksforGeeks" 
                style="padding: 5px 15px;">
        </template>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxTP").jqxTimePicker({
                width: 400,
                height: 400,
                footer: true,
                footerTemplate: "TempBtn"
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/5a0f12644b24350a2e219b8f02e75905.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-time picker-入门. htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-timepicker-getting-started.htm)