# jqwidgets jqxnombinput val()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnumber input-val-method/](https://www.geeksforgeeks.org/jqwidgets-jqxnumberinput-val-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxNumberInput 表示一个 jQuery 小部件，用于添加输入货币、百分比和任何类型的数字数据。输入数据可以以各种方式呈现。这个小部件的其他功能是自定义数字和小数位数、货币符号的字符串和位置、组和小数分隔符。

**val()** 方法用于设置或返回小部件的值。它接受字符串类型的单个参数值，并返回字符串类型的值。

**语法:**

设置小部件的值。

```html
$('Selector').jqxNumberInput('val', value); // or
$('Selector').val(value);
```

返回小部件的值。

```html
var value = $('Selector').jqxNumberInput('val'); // or
var value = $('Selector').val();
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

**示例:**下面的示例说明了 jQWidgets jqxnumber input**val()**方法。

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
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxnumberinput.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxNumberInput val() Method
        </h3>

        <div id='jqxNumberInput'></div>

        <input type="button" id="jqxBtn" 
            value="Set the Value" 
            style="padding: 5px 15px; margin-top: 50px;">
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxNumberInput").jqxNumberInput({
                width: '250px',
                height: '35px',
                spinButtons: true,
                value: 500
            });

            $("#jqxBtn").on('click', function() {
                $("#jqxNumberInput").jqxNumberInput('val', 3463.54);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/6e599118b74d3ce4f4ff8f2a0ac2d2b0.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnumber input/jquery-number-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnumberinput/jquery-number-input-api.htm)