# jQWidgets jqxListBox 源属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-source-property/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-source-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**源属性**用于设置或返回项目源。它接受数组类型值，默认值为 null。

**语法:**

要设置*源*属性:

```html
$("#jqxListBox").jqxListBox({source: data});
```

要获取*源*属性:

```html
var source = $('#jqxListBox').jqxListBox('source'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**以下示例说明了 jQWidgets 中的 jqxListBox **源**属性。

## 超文本标记语言

```html
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
                jQWidgets jqxListBox source Property
            </h3>
            <div id="jqxLB"></div>
            <br />
        </center>

        <script type="text/javascript">
            $(document).ready(function () {
                var data = 
                    ["C", "CSS", "C++", "Java"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "80px"
                });
            });
        </script>
    </body>
</html>
```

**输出:**

![](img/b95e1b534cac28c685158d3f24fb271c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm)