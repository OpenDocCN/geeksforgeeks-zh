# jQWidgets jqxInput val()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxinput-val-method/](https://www.geeksforgeeks.org/jqwidgets-jqxinput-val-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxInput 用于表示包含自动完成功能的 jQuery 输入小部件

**val()方法**用于设置或返回 jqxInput 小部件的输入值。它接受字符串类型的单参数值，并返回单值字符串。

**语法:**

设置值。

```html
$('Selector').jqxInput('val', 'New Value'); or 
$('Selector').val('New Value');
```

返回值。

```html
var value = $('Selector').jqxInput('val'); or 
var value = $('Selector').val();
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

下面的例子说明了 jQWidgets 中的 jqxInput val()方法。

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
        src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxinput.js">
    </script>
</head>

<body class='default'>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxInput val() Method
        </h3>
        <br>

        <label for="css">Enter Text: </label>
        <input type="text" id="GFG" />
        <br>
        <input type="button" id='jqxBtn' 
            value="Set the Value" 
            style="padding: 5px 15px; margin-top: 50px;" />
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

            $("#GFG").jqxInput({
                source: data,
                placeHolder: "Enter Subject..."
            });

            $('#jqxBtn').on('click', function () {
                $('#GFG').jqxInput('val', 'GeeksforGeeks');
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/a5b7fea19b0b95d7da8ae9733d2e2967.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxinput/jquery-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxinput/jquery-input-api.htm)