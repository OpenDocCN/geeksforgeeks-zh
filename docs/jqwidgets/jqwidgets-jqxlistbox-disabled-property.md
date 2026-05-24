# jQWidgets jqxListBox 禁用属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-disabled-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-disabled-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

*禁用* 属性用于启用或禁用所述列表框。它是布尔类型，默认值为*假*。

**语法:**

要设置*禁用的*属性:

```html
$('#jqxListBox').jqxListBox({ disabled: true });  
```

要禁用*属性:*

```html
*var disabled = $('#jqxListBox').jqxListBox('disabled');*
```

***链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。*

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> *<脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore*

***示例:**下面的示例说明了 jQWidgets 中的 jqxListBox *禁用了*属性。*

## *超文本标记语言*

```html
*<!DOCTYPE html>
<html lang="en">
    <head>
        <link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
        <script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
        <script type="text/javascript" src="jqwidgets/jqx-all.js"></script>
        <script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
        <script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
        <script type="text/javascript" src="jqwidgets/jqxscrollbar.js"></script>
        <script type="text/javascript" src="jqwidgets/jqxlistbox.js"></script>
    </head>

    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>

            <h3>
                jQWidgets jqxListBox disabled Property
            </h3>

            <div id="jqxLB"></div>
            <br />
            <input type="button" id="jqxBtn" 
                style="padding: 5px 20px;" value="Boolean" />
            <div id="log"></div>
        </center>

        <script type="text/javascript">
            $(document).ready(function () {
                var data = ["C", "CSS", "C++"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "80px",
                    disabled: true
                });

                $("#jqxBtn").on("click", function () {
                    var d = $("#jqxLB").jqxListBox("disabled");
                    $("#log").text(d);
                });
            });
        </script>
    </body>
</html>*
```

***输出:***

*![](img/7e7845e34d09ddeba9f379eec2a8dd60.png)

禁用的属性* 

***参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm?search=)*