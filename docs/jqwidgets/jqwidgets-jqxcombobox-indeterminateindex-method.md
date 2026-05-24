# jQWidgets jqxComboBox 不确定指数()方法

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxcombobox-inderedendex-method/](https://www.geeksforgeeks.org/jqwidgets-jqxcombobox-indeterminateindex-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 *jqxComboBox* 用于表示一个 jQuery combobox 小部件，它包含一个具有自动完成功能的输入字段和一个显示在下拉列表中的可选项目列表。

*不确定索引()*方法用于根据复选框项目的索引将其状态设置为不确定。当“复选框”属性设置为*真*时，应用此方法。该复选框使用基于 0 的索引。它接受数字类型的单个参数索引，并且不返回任何值。

**语法:**

```html
$('selector').jqxComboBox('indeterminateIndex', index);
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcjqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxlistbox . js "></script>
> <script type

**示例:**下面的示例说明了 jQWidgets 中的 jqxComboBox indeterminateIndex()方法。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
"jqwidgets/styles/jqx.base.css" 
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
            src="jqwidgets/jqxcolorpicker.js">
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
    <script type="text/javascript" 
            src="jqwidgets/jqxcombobox.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxComboBox indeterminateIndex() Method
        </h3>

        <div id='jqxCB'></div>
        <br>
        <input type="button" id='jqxBtn' 
            style="padding: 5px 20px;"
            value="indeterminateIndex" />
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
                "Bootstrap"
            ];

            $("#jqxCB").jqxComboBox({
                source: data,
                width: '250px',
                animationType: 'slide',
                checkboxes: true
            });

            $('#jqxBtn').on('click', function () {
                var popup = $("#jqxCB").jqxComboBox('indeterminateIndex', 4);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9f42b14085079a18eaec5fb0b2348762.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcombobox/jquery-combobox-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcombobox/jquery-combobox-api.htm)