# jQWidgets jqxnumber input readOnly 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnumberinput-readonly-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnumberinput-readonly-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxNumberInput 表示一个 jQuery 小部件，用于添加输入货币、百分比和任何类型的数字数据。输入数据可以以各种方式呈现。这个小部件的其他功能是自定义数字和小数位数、货币符号的字符串和位置、分组和小数分隔符。

**只读属性**用于设置或返回输入小部件的只读状态。它接受布尔类型值，默认值为 false。

**语法:**

设置 readOnly 属性。

```html
$('selector').jqxNumberInput({ readOnly: Boolean });
```

返回 readOnly 属性。

```html
var readOnly = $('selector').jqxNumberInput('readOnly');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets jqxnumber input readOnly 属性。

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
        src="jqwidgets/jqxnumberinput.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxNumberInput readOnly Property
        </h3>

        <div id='jqxNumberInput'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxNumberInput").jqxNumberInput({
                width: '250px',
                height: '35px',
                spinButtons: true,
                readOnly: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/79089724fa0c5067425c5a445ae8b810.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnumber input/jquery-number-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnumberinput/jquery-number-input-api.htm)