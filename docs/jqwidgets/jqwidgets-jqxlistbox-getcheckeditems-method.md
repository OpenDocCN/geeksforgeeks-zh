# jqwidgets jqxlistox getchechkeditems()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-getcheckeditems-method/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-getcheckeditems-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**getCheckedItems()** 方法用于从所述列表中返回被检查的项目。此外，返回的输出是一个由选中项组成的数组。它没有参数，并且返回数组。

返回值是具有以下字段的对象。

*   标签
*   价值
*   有缺陷的
*   检查
*   hasThreeStates
*   超文本标记语言
*   指数
*   组

**语法:**

```html
var items = $("#jqxListBox").jqxListBox('getCheckedItems');  
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**下面的示例说明了 jQWidgets 中的 jqxListBox**getCheckedItems()**方法。

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
            jQWidgets jqxListBox getCheckedItems() Method
        </h3>

        <div id="jqxLB"></div>
        <br />
        <input type="button" id="jqxBtn" 
            style="padding: 5px 20px;" 
            value="get the checked items" />
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var data = ["CSS", "C", "C++ Programming"];

            $("#jqxLB").jqxListBox({
                source: data,
                width: "200px",
                height: "80px",
                checkboxes: true,
                multiple: true,
            });

            $("#jqxLB").jqxListBox("checkItem", "C");
            $("#jqxLB").jqxListBox("checkItem", "CSS");

            $("#jqxBtn").on("click", function () {
                var itms = $("#jqxLB").jqxListBox("getCheckedItems");
                if (itms.length > 0) {
                    var labls = "";
                    for (var n = 0; n < itms.length; n++) {
                        labls += itms[n].label;
                        if (n < itms.length - 1) labls += ", ";
                    }
                    console.log(labls);
                }
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/d56bc296fb1d05e3cb0efbcae2661d3c.png)

getCheckedItems 方法

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm?search=)