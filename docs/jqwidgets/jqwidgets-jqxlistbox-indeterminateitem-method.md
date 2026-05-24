# jQWidgets jqxListBox indeterminateItem（） Method

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxlistbox-indendestitem-method/](https://www.geeksforgeeks.org/jqwidgets-jqxlistbox-indeterminateitem-method/)

**简介:jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxListBox 用于说明一个 jQuery ListBox 小部件，它包含一个可选择元素的列表。

**不确定项()方法**用于不确定 *jqxListBox* 的所述项目。它不返回任何东西。

**语法:**

```html
$("#jqxListBox").jqxListBox('indeterminateItem', item);
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **项:**是类型对象或字符串的规定项

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore

**示例:**下面的示例说明了 jQWidgets 中的 jqxListBox**indendestitem()**方法。

## 超文本标记语言

```html
<html>
    <head>
        <link rel="stylesheet" 
              href="jqwidgets/styles/jqx.base.css" 
              type="text/css" />
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
                jQWidgets jqxListBox indeterminateItem() Method
            </h3>
            <div id="jqxLB"></div>
            <br />
            <input type="button" id="jqxBtn" 
                   style="padding: 5px 20px;" 
                   value="Indeterminate C++ Programming" />
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
                  "JavaScript"];

                $("#jqxLB").jqxListBox({
                    source: data,
                    width: "200px",
                    height: "100px",
                    checkboxes: true
                });

                $("#jqxBtn").on("click", function () {
                    $("#jqxLB")
                      .jqxListBox("indeterminateItem",
                                  "C++ Programming" );
                });
            });
        </script>
    </body>
</html>
```

**输出:**

![](img/887a7ac02e5f8b43075f04cd5c065824.png)

不确定项目法

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxlistbox/jquery-listbox-api.htm)