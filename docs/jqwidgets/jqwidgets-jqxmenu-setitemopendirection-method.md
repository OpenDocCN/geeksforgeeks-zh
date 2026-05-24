# jQWidgets jqxMenu setiteopendirection()方法

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxmenu-setiteopendirection-method/](https://www.geeksforgeeks.org/jqwidgets-jqxmenu-setitemopendirection-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxMenu 代表一个 jQuery 菜单小部件，用于创建网站或 web 应用程序的菜单。jqxMenu 小部件可以用来创建网站菜单、定制的上下文菜单或应用程序风格的菜单栏，只需少量的脚本。

**setItemOpenDirection()方法**用于设置小部件的项目弹出打开方向。它接受下面讨论三个参数:

*   **项:**指定字符串类型菜单项的 id。
*   **水平方向:**指定菜单小部件的水平方向。它是字符串类型值。
*   **垂直方向:**指定菜单小部件的垂直方向。它是字符串类型值。

**返回值:**不返回值。

**语法:**

```html
$('Selector').jqxMenu('setItemOpenDirection', 
    'Services', 'right', 'up');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets jqxMenu destroy()方法。

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
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxmenu.js"></script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #jqxMenu {
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
        jQWidgets jqxMenu setItemOpenDirection() Method
    </h3>

    <div id='jqxWidget'>
        <div id='jqxMenu'>
            <ul>
                <li><a href="#">GeeksforGeeks</a></li>
                <li>Programming Languages
                    <ul>
                        <li><a href="#">C</a></li>
                        <li><a href="#">C++</a></li>
                        <li><a href="#">Java</a></li>
                        <li><a href="#">Python</a></li>
                        <li><a href="#">C#</a></li>
                    </ul>
                </li>
                <li id="web">Web Technology
                    <ul>
                        <li><a href="#">Frontend</a>
                            <ul>
                                <li><a href="#">HTML</a></li>
                                <li><a href="#">CSS</a></li>
                                <li><a href="#">JavaScript</a></li>
                                <li><a href="#">ReactJS</a></li>
                            </ul>
                        </li>
                        <li><a href="#">Backend</a>
                            <ul>
                                <li><a href="#">PHP</a></li>
                                <li><a href="#">Node.js</a></li>
                            </ul>
                        </li>
                    </ul>
                </li>
                <li><a href="#">Data Structure</a></li>
                <li><a href="#">Algorithm</a></li>
            </ul>
        </div>
    </div>

    <center>
        <input type="button" value="Set Item Open Direction" 
            id="jqxBtn" 
            style="padding: 5px 15px; margin-top: 130px;">
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxMenu").jqxMenu({
                theme: 'energyblue',
                width: '650'
            });

            $('#jqxBtn').on('click', function() {
                $("#jqxMenu").jqxMenu('setItemOpenDirection',
                    'web', 'right', 'up');
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/185531ce681e8570619e36ae9a5e4de4.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxmenu/jquery-menu-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxmenu/jquery-menu-api.htm)