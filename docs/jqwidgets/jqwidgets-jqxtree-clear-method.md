# jQWidgets jqxTree clear()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtree-clear-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtree-clear-method/)

jQWidgets 是一个 JavaScript 框架，用于为 pc 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxTree 代表一个 jQuery 小部件，用于显示项目的分层集合。要显示项目集合，我们可以从“UL”或使用其“源”属性进行填充。

**clear()方法**用于移除小部件中的所有元素。它不接受任何参数，也不返回值。

**语法:**

```html
$('Selector').jqxTree('clear');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery-1 . 11 . 1 . min . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqx-1

下面的例子说明了 jQWidgets jqxTree clear()方法。

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
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxpanel.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtree.js"></script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #jqxTree {
            width: 100%;
            margin: 0 auto;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxTree clear() Method
    </h3>

    <div id='jqxTree'>
        <ul>
            <li item-selected='true'>
                GeeksforGeeks
            </li>

            <li>Programming
                <ul>
                    <li>C</li>
                    <li>C++</li>
                    <li>Java</li>
                    <li>Python</li>
                </ul>
            </li>

            <li>Web Technology
                <ul>
                    <li>HTML</li>
                    <li>CSS</li>
                    <li>JavaScript</li>
                    <li>jQuery</li>
                    <li>PHP</li>
                </ul>
            </li>
        </ul>
    </div>

    <center>
        <input type="button" id="jqxBtn" 
            value="Clear Items" 
            style="padding: 5px 15px; margin-top: 20px;">
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxTree').jqxTree({
                width: '350px',
                height: '250px'
            });
        });

        $("#jqxBtn").on('click', function() {
            $('#jqxTree').jqxTree('clear');
        });
    </script>
</body>

</html>
```

**输出:**

![](img/d35f4bb8acae3010597d86999ff78107.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtree/jquery-tree-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtree/jquery-tree-api.htm)