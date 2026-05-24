# jQWidgets jqxDropDownList getItem()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxddropdownlist-getitem-method/](https://www.geeksforgeeks.org/jqwidgets-jqxdropdownlist-getitem-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxDropDownList 小部件是一个 jQuery 下拉列表，其中包含下拉列表中显示的可选项目列表。

getItem()方法用于通过使用索引号来获取该项。它接受数字类型的单个参数索引，并且不返回任何值。

返回值项具有以下字段:

*   **标签–**指定物品的标签。
*   **值–**指定项目的值。
*   **禁用–**指定项目是否启用/禁用。
*   **已勾选–**指定项目是否已勾选/未勾选。
*   **hasthreads–**指定复选框项支持三种状态。
*   **html–**指定 HTML 中的显示项。它可以用来代替标签。
*   **索引–**指定项目索引号。
*   **组–**指定项目的组。

**语法:**

```html
$("Selector").jqxDropDownList('getItem', index);
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> 脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "【T16

下面的例子说明了 jQWidgets 中的 jqxDropDownList getItem()方法。

**示例:**

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
            jQWidgets jqxDropDownList getItem() Method
        </h3>

        <div id='jqxDDL'></div>

        <input id="jqxBtn" type="button" 
            value="Get Item of Given Index" 
            style="padding: 5px 15px; margin-top: 50px;">
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
                theme: 'energyblue'
            });

            $("#jqxBtn").on('click', function() {
                var item = $("#jqxDDL").jqxDropDownList('getItem', 3);

                alert("Item Label: " + item.label);
            });
        });
    </script>
</body>

</html
```

**输出:**

![](img/97a31e95ab266674b206f8523b5efa77.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdropdownlist/jquery-dropdownlist-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdropdownlist/jquery-dropdownlist-api.htm)