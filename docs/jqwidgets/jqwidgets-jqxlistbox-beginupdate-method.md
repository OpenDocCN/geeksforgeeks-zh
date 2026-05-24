# jqwidgets jqxlistox begin update()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-beginupdate-method/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-beginupdate-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**beginUpdate()** 方法用于阻止列表框的解释。此外，当需要动态插入或删除几个元素时，通常会用到它。

**语法:**

```html
$("#jqxListBox").jqxListBox('beginUpdate'); 
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**下面的示例说明了 jQWidgets 中的 jqxListBox beginUpdate()方法。

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
        src=".jqwidgets/jqxbuttons.js"></script>
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
            jQWidgets jqxListBox beginUpdate() Method
        </h3>

        <div id="jqxLB"></div>
        <br />
        <input type="button" id="jqxBtn" 
            style="padding: 5px 20px;" 
            value="Add items" />
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
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
                "Bootstrap"];

            $("#jqxLB").jqxListBox({
                source: data,
                width: "200px",
                height: "200px",
            });

            $("#jqxBtn").on("click", function () {
                $("#jqxLB").jqxListBox("beginUpdate");
                $("#jqxLB").jqxListBox("addItem", "item 1");
                $("#jqxLB").jqxListBox("addItem", "item 2");
                $("#jqxLB").jqxListBox("addItem", "item 3");
                $("#jqxLB").jqxListBox("addItem", "item 4");
                $("#jqxLB").jqxListBox("endUpdate");
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/99222620389fe371f183c39e1cf62e03.png)

beginUpdate()方法

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm?search=)