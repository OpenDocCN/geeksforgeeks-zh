# jQWidgets jqxListBox filter placeholder 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-filter placeholder-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-filterplaceholder-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**过滤器占位符属性**用于检查过滤器输入的占位符。它的类型为字符串，默认值为“查找”。

**语法:**

要设置*过滤器占位符*属性:

```html
$("#jqxListBox").jqxListBox({filterPlaceHolder:300}); 
```

要获取*过滤器占位符*属性:

```html
var filterPlaceHolder = 
    $('#jqxListBox').jqxListBox('filterPlaceHolder'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcorejqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxlistbox . js ">/script>

下面的例子说明了 jQWidgets 中的 jqxListBox**filter placeholder**属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" 
              href="jqwidgets/styles/jqx.base.css" 
              type="text/css" />
        <script type="text/javascript"
                src="scripts/jquery-1.11.1.min.js">
        </script>
        <script type="text/javascript" 
                src="jqwidgets/jqx-all.js">
        </script>
        <script type="text/javascript" 
                src="jqwidgets/jqxcore.js">
        </script>
        <script type="text/javascript" 
                src="jqwidgets/jqxbuttons.js">
        </script>
        <script type="text/javascript" 
                src="jqwidgets/jqxscrollbar.js">
        </script>
        <script type="text/javascript" 
                src="jqwidgets/jqxlistbox.js">
        </script>
    </head>
    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>

            <h3>
                jQWidgets jqxListBox 
                filterPlaceHolder Property
            </h3>

            <div id="jqxLB"></div>
            <br />
            <input type="button" id="jqxBtn" 
                   style="padding: 5px 20px;" 
                   value="filter's placeholder" />
            <div id="log"></div>
        </center>

        <script type="text/javascript">
            $(document).ready(function () {
                var data = ["C", "CSS", "C++"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "80px",
                    filterPlaceHolder: "Filter",
                    filterable: true
                });

                $("#jqxBtn").on("click", function () {
                    var fp = $("#jqxLB")
                        .jqxListBox("filterPlaceHolder");
                    $("#log").text(fp);
                });
            });
        </script>
    </body>
</html>
```

**输出:**

![](img/a2fc4d28681ea064cbbde8b67f0e4453.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm)