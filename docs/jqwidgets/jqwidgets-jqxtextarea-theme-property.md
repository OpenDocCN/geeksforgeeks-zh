# jQWidgets jqxTextArea 主题属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxtextarea-theme-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtextarea-theme-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxTextArea 表示一个 jQuery Textarea 小部件，用于在文本框中插入文本内容。

*主题*属性用于设置或返回 jqxTextArea 小部件的主题。它接受字符串类型值，默认值为空(" ")。要使用这个属性，首先我们需要在标题部分包含主题样式表**(*****【jqx . energy blue . CSS】***)。主题文件包括在 *jqx.base.css* 文件之后。

**语法:**

*   设置*主题*属性。

    ```html
    $('selector').jqxTextArea({ theme: String });
    ```

*   返回*主题*属性。

    ```html
    var theme = $('selector').jqxTextArea('theme');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/.) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "【T15jqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxscrollbar . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtextarea . js ">/script>

**示例:**以下示例说明了 jQWidgets jqxTextArea *主题*属性。

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
            jQWidgets jqxTextArea theme Property
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
                theme: 'energyblue',
                source: data,
                width: 250,
                height: 100,
                placeHolder: 'Enter Subjects...'
            })
        });
    </script>
</body>

</html>
```

**输出:**

![](img/16295727b729e134bddb34bf89327346.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtextarea/jquery-textarea-api.htm)