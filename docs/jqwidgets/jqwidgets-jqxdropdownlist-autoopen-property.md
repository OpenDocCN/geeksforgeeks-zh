# jQWidgets jqxDropDownList 自动打开属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxddropdownlist-auto open-property/](https://www.geeksforgeeks.org/jqwidgets-jqxdropdownlist-autoopen-property/)

**简介:jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxDropDownList 小部件是一个 jQuery 下拉列表，其中包含下拉列表中显示的可选项目列表。

*自动打开*属性用于设置或返回当鼠标光标在小部件上移动时是否自动打开下拉选项。它接受布尔类型值，默认值为*假*。

**语法:**

设置*自动打开*属性。

```html
$('selector').jqxDropDownList({ autoOpen: Boolean });
```

返回*自动打开*属性。

```html
var autoOpen = $('selector').jqxDropDownList('autoOpen');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/.) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> 脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "【T16

**示例:**以下示例说明了 jQWidgets 中的 jqxDropDownList *自动打开*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css">
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxlistbox.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdropdownlist.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxDropDownList autoOpen Property
        </h3>

        <div id='jqxDDL'></div>
    </center>
    <script type="text/javascript">
        $(document).ready(function() {
            var data = [
                "Computer Science",
                "C Programming",
                "C++ Programming",
                "Java Programming",
                "Python Programming",
                "HTML",
                "CSS",
                "JavaScript",
                "jQuery",
                "PHP",
                "Bootstrap"
            ];

            $("#jqxDDL").jqxDropDownList({
                source: data,
                theme: 'energyblue',
                autoOpen: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/44109559f0708e4aaf2e31ca4754431d.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation//jquery-dropdownlist-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation//jquery-dropdownlist-api.htm)