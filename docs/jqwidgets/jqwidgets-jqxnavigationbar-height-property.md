# jQWidgets jqxNavigationBar 高度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnavigationbar-height-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-height-property/)

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxNavigationBar*** 用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

***高度*** 属性用于设置或获取指定 jqxNavigationBar 的高度。该属性接受一些可能的值，如“自动”或类似“Npx”的字符串，其中 N 是任意数字或以像素为单位的数值。

**语法:**

*   用于设置 ***高度*** 属性:

    ```html
    $('Selector').jqxNavigationBar({ height: 132 });  
    ```

*   获取 ***高度*** 属性:

    ```html
    var height = $('Selector').jqxNavigationBar('height');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><

**示例:**以下示例说明了 jQWidgets jqxNavigationBar***高度*** 属性。在下面的示例中， ***高度*** 属性的值被设置为 132。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css"
          type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxexpander.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxnavigationbar.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxNavigationBar height Property
        </h3>
        <div id="jqx_Navigation_Bar" style="margin: 25px;" 
             align="left">
            <div>First Header</div>
            <div>
                <h8>Content for the first header</h8>
                <ul>
                    <li>GFG</li>
                    <li>CSE</li>
                </ul>
            </div>
            <div> Second Header</div>
            <div>
                <h8>Content for the second header</h8>
                <ul>
                    <li>GeeksforGeeks</li>
                    <li>CSE</li>
                </ul>
            </div>
        </div>
        <input type="button" style="margin: 29px;" 
               id="jqxbutton_for_height" 
               value="Value of the height property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 132
                    });
                $("#jqxbutton_for_height").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_height').
                    on('click', function () {
                        var value_of_height =
                            $('#jqx_Navigation_Bar').
                                jqxNavigationBar(
                                    'height');
                        $("#log").html(JSON.stringify(
                            value_of_height))
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/caf3bda862a082c7ee006dddb2bdfe8e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm?search=)