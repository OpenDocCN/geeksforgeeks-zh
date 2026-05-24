# jQWidgets jqxTextArea 搜索模式属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxtextarea-search mode-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtextarea-searchmode-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxTextArea 表示一个 jQuery Textarea 小部件，用于在文本框中插入文本内容。

*搜索模式*属性用于设置或返回搜索模式。当用户键入文本区域，并尝试使用输入的文本和选定的搜索模式查找搜索到的项目时，将使用此属性。它接受字符串类型值，其默认值为“默认值”。

*搜索模式*属性的可能值如下。

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

*   设置*搜索模式*属性。

    ```html
    $('selector').jqxTextArea({ searchMode: String });
    ```

*   返回*搜索模式*属性。

    ```html
    var searchMode = $('selector').jqxTextArea('searchMode');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcorejqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtextarea . js ">/script>

**示例:**以下示例说明了 jQWidgets jqxTextArea *搜索模式*属性。

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
            src=".jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxtextarea.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxTextArea searchMode Property
        </h3>

        <textarea id='jqxTA'></textarea>
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

            $('#jqxTA').jqxTextArea({
                source: data,
                width: 250,
                height: 100,
                placeHolder: 'Enter Subjects...',
                searchMode: 'startswith'
            })
        });
    </script>
</body>

</html>
```

**输出:**

![](img/439bc27328869da7ae48352780430be5.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-api.htm)