# jqwidgets jqxlistox 滤波器的特性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-filter delay-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-filterdelay-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**滤波器延迟属性**用于检查滤波器的延迟。这里，所述小部件基于过滤器输入的值在 100 毫秒后自发地过滤其数据。为了仅在“*输入*按键上执行*过滤*，您需要将该属性值设置为零。它属于数字类型，默认值为 100。

**语法:**

要设置*过滤延迟*属性:

```html
$("#jqxListBox").jqxListBox({filterDelay:300}); 
```

要获取*过滤器延迟*属性:

```html
var filterDelay = $('#jqxListBox').jqxListBox('filterDelay'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**以下示例说明了 jQWidgets 中的 jqxListBox **filterDelay** 属性。

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
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxlistbox.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxListBox filterDelay Property
        </h3>

        <div id="jqxLB"></div>
        <br />
        <input type="button" id="jqxBtn" 
            style="padding: 5px 20px;" 
            value="filter's delay" />
        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var data = ["C", "CSS", "C++"];

            $("#jqxLB").jqxListBox({
                source: data,
                width: "200px",
                height: "80px",
                filterDelay: 400,
                filterable: true
            });

            $("#jqxBtn").on("click", function () {
                var fd = $("#jqxLB").jqxListBox("filterDelay");
                $("#log").text(fd);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/a86fb26b3629b6aa9840806d951d86e3.png)

filterDelay 属性

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm?search=)