# jQWidgets jqxEditor 可编辑属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxeditor-可编辑-property/](https://www.geeksforgeeks.org/jqwidgets-jqxeditor-editable-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxEditor 用于表示 jQuery HTML 文本编辑器，该编辑器可用于简化网页内容创建，也可用于替代 HTML 文本区域。

**可编辑属性**用于设置或返回可编辑属性，即编辑器可以设置为可编辑或不可编辑。它接受布尔类型值，默认值为真。

**语法:**

设置可编辑属性。

```html
$('Selector').jqxEditor({ editable: Boolean });  
```

返回可编辑属性。

```html
var editable = $('Selector').jqxEditor('editable');
```

**链接文件:**从 https://www.jqwidgets.com/download/链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> T21】脚本类型=【text/JavaScript】src =【jqwidgets/jqxbuttons。 >
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxeditor . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxtooltip . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxc

以下示例说明了 jQWidgets 中的 jqxEditor 可编辑属性:

**示例:**

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
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxlistbox.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdropdownlist.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdropdownbutton.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcolorpicker.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxwindow.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxeditor.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtooltip.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcheckbox.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxEditor editable Property</h3>

        <textarea id="editor"></textarea>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#editor').jqxEditor({
                height: "400px",
                width: '700px',
                editable: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9dfb94d19090a1a952d97cd0c5819e11.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-api.htm?search=)