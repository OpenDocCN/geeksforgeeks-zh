# jQWidgets jqxListBox 多重扩展属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-multipleextended-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-multipleextended-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**多重扩展属性**用于使用 *Shift* 和 *Ctrl* 键启用或禁用所述列表框的项目的多重选择。因此，只要此处的值设置为 true，用户就可以通过点击给定的项目并按住 Shift 或 Ctrl 键从列表框中选择多个项目。它属于布尔类型，默认值为假。

**语法:**

要设置*多重扩展*属性:

```html
$("#jqxListBox").jqxListBox({multipleextended: true}); 
```

要获得*多重扩展*属性:

```html
var multipleextended = 
    $('#jqxListBox').jqxListBox('multipleextended'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcorejqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxlistbox . js ">/script>

下面的例子说明了 jQWidgets 中的 jqxListBox**multipleextended**属性。

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
                multipleextended Property
            </h3>
            <div id="jqxLB"></div>
            <br />
            <input type="button" id="jqxBtn" 
                   style="padding: 5px 20px;" 
                   value="Boolean" />
            <div id="log"></div>
        </center>

        <script type="text/javascript">
            $(document).ready(function () {
                var data = ["C", "CSS", "C++"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "80px",
                    multipleextended: true
                });

                $("#jqxBtn").on("click", function () {
                    var me = $("#jqxLB").jqxListBox(
                      "multipleextended"
                    );
                    $("#log").text(me);
                });
            });
        </script>
    </body>
</html>
```

**输出:**

![](img/1bc09d2ab32622543a9721d6e13c113c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm)