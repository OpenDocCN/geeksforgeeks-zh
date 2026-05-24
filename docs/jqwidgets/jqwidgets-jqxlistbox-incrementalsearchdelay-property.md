# jqwidgets jqxlistox 增量式阿奇 Delay Property

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-incrementalsearchdelay-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-incrementalsearchdelay-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**增量搜索延迟属性**用于设置或返回*增量搜索延迟*属性。此属性以毫秒为单位描述了删除前一个搜索字符串后的时间段。在这里，一旦我们停止打字，计时器就开始计时。它的类型是数字，默认值是 700。

**语法:**

要设置*增量搜索延迟*属性:

```html
$("#jqxListBox").jqxListBox({incrementalSearchDelay: 400});
```

要获取*增量搜索延迟*属性:

```html
var incSearchDel = $('#jqxListBox').jqxListBox('incrementalSearchDelay'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**下面的示例说明了 jQWidgets 中的 jqxListBox**incrementalsarchdelay**属性。

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
            jQWidgets jqxListBox incrementalSearchDelay Property
        </h3>

        <div id="jqxLB"></div>
        <br />
        <input type="button" id="jqxBtn" 
            style="padding: 5px 20px;" value="Delay in ms" />
        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var data = ["C", "CSS", "C++", "Java"];

            $("#jqxLB").jqxListBox({
                source: data,
                width: "200px",
                height: "80px",
                incrementalSearch: true,
                incrementalSearchDelay: 200,
                filterable: true
            });

            $("#jqxBtn").on("click", function () {
                var isd = $("#jqxLB")
                    .jqxListBox("incrementalSearchDelay");

                $("#log").text(isd);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/82a00707ce0db07fd601e607fd7a4586.png)

增量搜索延迟属性

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm?search=)