# jQWidgets jqxListBox ensureVisible()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-ensurevisible-method/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-ensurevisible-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**确保可见()方法**用于确保所述项目是否可见。如有必要，此方法将向该项滚动。此外，还可以传递项的值来代替索引。它支持一个可选的布尔参数，该参数表示是否将所述项目准备为所述列表中最高可见的项目。它不返回任何东西。

**语法:**

```html
$("#jqxListBox").jqxListBox('ensureVisible', index);  
$("#jqxListBox").jqxListBox('ensureVisible', "value of the Index");
```

**参数:**

*   **项目:**所述类型号、字符串或对象的项目。

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**下面的示例说明了 jQWidgets 中的 jqxListBox**ensureVisible()**方法。

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
                src=".jqwidgets/jqxbuttons.js">
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
                jQWidgets jqxListBox ensureVisible() Method
            </h3>
            <div id="jqxLB"></div>
            <br />
            <input type="button" id="jqxBtn" 
                   style="padding: 5px 20px;"
                   value="Move to the fifth element" />
        </center>
        <script type="text/javascript">
            $(document).ready(function () {
                var data = [
                "Computer Science",
                "C Programming",
                "CSS", 
                "Java Programming", 
                "Python Programming",
                "Scala"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "100px",
                });
                $("#jqxLB").jqxListBox("disableAt", 3);
                $("#jqxBtn").on("click", function () {
                    $("#jqxLB").jqxListBox("ensureVisible", 5);
                });
            });
        </script>
    </body>
</html>
```

**输出:**

![](img/164f058cec24ec359021f4fdb03f429a.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm)