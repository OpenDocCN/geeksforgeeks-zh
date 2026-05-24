# jQWidgets jqxnumber input group separator 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnumberinput-group separator-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnumberinput-groupseparator-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxNumberInput 表示一个 jQuery 小部件，用于添加输入货币、百分比和任何类型的数字数据。输入数据可以以各种方式呈现。这个小部件的其他功能是自定义数字和小数位数、货币符号的字符串和位置、组和小数分隔符。

**组分隔符属性**用于设置或返回分隔输入字段数字组的字符串。它将数值中小数点左边的数字分开。它接受字符类型值，默认值为'，'

**语法:**

设置 groupSeparator 属性。

```html
$('selector').jqxNumberInput({ groupSeparator: Char });
```

返回 groupSeparator 属性。

```html
var groupSeparator = $('selector').jqxNumberInput('groupSeparator');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

下面的例子说明了 jQWidgets jqxnumber input group separator 属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" src=
        "scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxnumberinput.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxNumberInput groupSeparator Property
        </h3>

        <div id='jqxNumberInput'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxNumberInput").jqxNumberInput({
                width: '250px',
                height: '35px',
                groupSeparator: "-"
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/08a0178fcbc7aa4541d1faf3a5e2ba2b.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnumber input/jquery-number-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnumberinput/jquery-number-input-api.htm)