# jqwidgets jqxnnavigator get content()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jqwidgets-jqxnnavigation-get content-method/

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxNavigationBar*** 用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

***getContentAt()*** 方法用于获取具有给定项目索引的指定 jqxNavigationBar 的项目内容。

**语法:**

```html
$('Selector').jqxNavigationBar('getContentAt', Item_Index);
```

**参数:**该方法接受如下所示的参数:

*   **Item_Index:** 这是将要返回内容的项目的索引。

**返回值:**该方法返回内容的字符串值。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><

**示例:**下面的示例说明了 jQWidgets jqxNavigationBar**getContentAt()**方法。在下面的示例中，将返回第二项的内容。

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
            jQWidgets jqxNavigationBar getContentAt() Method
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
            <div>Content for the second header</div>
        </div>
        <input type="button" style="margin: 29px;" 
               id="jqxbutton_for_getContentAt"
            value="Get content of the second item"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 150,
                    });
                $("#jqxbutton_for_getContentAt").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_getContentAt').
                    on(
                        'click', function () {
                            var Content =
                                $('#jqx_Navigation_Bar').
                                    jqxNavigationBar(
                                        'getContentAt', 1);
                            $("#log").html(JSON.stringify(
                                Content))
                        });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/05ea48b1a1ebe1ddf01293177500a2ae.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm?search=)