# jqwidgets jqxnnavigator setheadcontentat()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jqwidgets-jqxnnavigation-setheadcontentat-method/上的 http://www . geeksforgeeks . org/jqwidgets-jqxnnavigation-setheadcontentat-method]

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxNavigationBar*** 用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

**setHeaderContentAt()** 方法用于为指定 jqxNavigationBar 的特定项目设置新的标题内容。

**语法:**

```html
$('Selector').jqxNavigationBar(
    'setHeaderContentAt', Item_Index, Item);
```

**参数:**该方法接受两个参数，如下图所示:

*   **Item_Index:** 这是将设置新表头内容的项目的索引。
*   **项:**这是新的表头内容。

**返回值:**此方法不返回值。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><

**示例:**下面的示例说明了 jQWidgets jqxNavigationBar***setHeaderContentAt()***方法。在下面的示例中，正在为第 0 个项目设置新的标题内容。

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
            jQWidgets jqxNavigationBar setHeaderContentAt() Method
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
               id="jqxbutton_for_setHeaderContentAt"
            value="Set a new header content for 0th item"/>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 150,
                    });
                $("#jqxbutton_for_setHeaderContentAt").
                    jqxButton({
                        width: 280,
                    });
                $('#jqxbutton_for_setHeaderContentAt').
                    on('click', function () {
                        var Item_Index = 0;
                        var Item = "New Header";
                        $('#jqx_Navigation_Bar').
                            jqxNavigationBar(
                                'setHeaderContentAt',
                                Item_Index, Item);
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/11fbe91db63cf7c56bf122ffb9f0537b.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm?search=)