# jQWidgets jqxformatedinput 基数属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxformatedinput-radix-property/](https://www.geeksforgeeks.org/jqwidgets-jqxformattedinput-radix-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxFormattedInput 是一个 jQuery 输入小部件，用于输入二进制、八进制、十进制或十六进制格式的数字。可以通过可选的旋转按钮增加/减少输入数字，也可以通过可选的弹出菜单改变数字系统。

**基数属性**用于设置或返回 jqxFormattedInput 小部件的基数。基数指定显示部件值的数字系统。它接受数字/字符串类型的值，默认值为 10。

它的可能值是–

*   2 或“二进制”
*   8 或“八进制”
*   10 或“十进制”
*   16 或“十六进制”

**语法:**

设置基数属性。

```html
$('selector').jqxFormattedInput({ radix: Number/String });
```

返回基数属性。

```html
var radix = $('selector').jqxFormattedInput('radix');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <script type = " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxcore . js

下面的例子说明了 jQWidgets jqxFormattedInput 基数属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxformattedinput.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxFormattedInput radix Property
        </h3>

        <div id="jqxFI">
            <input type="text" />
            <div></div>
            <div></div>
        </div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxFI").jqxFormattedInput({
                width: 300,
                height: 40,
                radix: "decimal",
                value: "121",
                spinButtons: true,
                dropDown: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/739f4f2b3b14c710685a2d11bfd673d9.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxformatedinput/jquery-formated-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxformattedinput/jquery-formatted-input-api.htm)