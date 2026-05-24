# jQWidgets jqxTextArea 打开属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxtextarea-open-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtextarea-opened-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxTextArea 表示一个 jQuery Textarea 小部件，用于在文本框中插入文本内容。

打开的*属性用于获取一个值，该值指示自动建议弹出窗口是否打开。它接受布尔类型值，默认值为*假*。*

***语法:***

*返回*打开的*属性。*

```html
*var opened = $('selector').jqxTextArea('opened');*
```

***链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。*

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> *<脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqx-all . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcorejqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtextarea . js ">/script>*

***示例:**以下示例说明了 jQWidgets jqxTextArea *打开的*属性。*

## *超文本标记语言*

```html
*<!DOCTYPE html>
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
            jQWidgets jqxTextArea opened Property
        </h3>

        <textarea id='jqxTA'></textarea>
        <br>
        <input type="button" id='jqxBtn' 
            style="padding: 5px 20px; margin-top: 160px;" 
            value="Check popup opened or not" />
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
                placeHolder: 'Enter Subjects...'
            })

            $('#jqxBtn').on('click', function () {
                var opened = $('#jqxTA').jqxTextArea('opened');

                if (opened) {
                    alert('Popup opened');
                } else {
                    alert('Popup not opened');
                }
            });
        });
    </script>
</body>

</html>*
```

***输出:***

*![](img/bd6ceb8179bf70b3b3916da214f5f204.png)*

***参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-api.htm)*