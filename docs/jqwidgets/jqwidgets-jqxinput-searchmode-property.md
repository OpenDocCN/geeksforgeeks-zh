# jQWidgets jqxInput 搜索模式属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxinput-search mode-property/](https://www.geeksforgeeks.org/jqwidgets-jqxinput-searchmode-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxInput 用于表示包含自动完成功能的 jQuery 输入小部件

**搜索模式属性**用于设置或返回搜索模式。当用户键入输入文本并尝试使用输入的文本和选定的搜索模式查找搜索到的项目时，将使用此属性。它接受字符串类型值，其默认值为“默认值”。

searchMode 属性的可能值如下。

*   没有
*   “包含”
*   '包含 ignorecase '
*   等于
*   ' equalsignorecase '
*   ' startswithignorecase '
*   '开始于'
*   ' endswithignorecase '
*   "结束"

**语法:**

设置搜索模式属性。

```html
$('selector').jqxInput({ searchMode: String });
```

返回搜索模式属性。

```html
var searchMode = $('selector').jqxInput('searchMode');
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "></脚本>
> 脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js

下面的例子说明了 jQWidgets 中的 jqxInput searchMode 属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
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
            jQWidgets jqxInput searchMode Property
        </h3>
        <br>

        <label for="css">Enter Text: </label>
        <input type="text" id="GFG" />
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
                placeHolder: "Enter Subject...",
                searchMode: 'startswith'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/ed3439f06a3560b740f9802826535b6e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxinput/jquery-input-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxinput/jquery-input-api.htm)