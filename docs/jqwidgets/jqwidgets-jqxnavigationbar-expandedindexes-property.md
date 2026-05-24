# jQWidgets jqxNavigationBar expandindexes 属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxnavigationbar-expandindexes-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-expandedindexes-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。****jqxNavigationBar**用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。**

****扩展索引**属性用于设置或获取指定 jqxNavigationBar 的扩展项。如果属性 **expandMode** 的值设置为“单个”、“单个高度”、“切换”或“无”，则只扩展与数组中第一个值对应的项。如果属性**扩展代码**的值设置为“单个”或“单个高度”，并且扩展索引数组为空，则第一项会自动扩展。**

****语法:****

*   **设置*扩展索引*属性:**

    ```html
    $('Selector').jqxNavigationBar({ 
        expandedIndexes: [1, 1] 
    });
    ```

*   **获取*扩展索引*属性:**

    ```html
    var expandedIndexes = 
        $('Selector').jqxNavigationBar('expandedIndexes');
    ```

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><**

****示例:**以下示例说明了 jQWidgets jqxNavigationBar**expandindexes**属性。在下面的示例中， ***扩展索引*** 属性的值已设置为[1，1]。**

## **超文本标记语言**

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
            jQWidgets jqxNavigationBar expandedIndexes Property
        </h3>
        <div id="jqx_Navigation_Bar" 
             style="margin: 25px;" 
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
               id="jqxbutton_for_expandedIndexes"
            value="Value of the expandedIndexes property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 250,
                        height: 132,
                        expandMode: 'singleFitHeight',
                        expandedIndexes: [1, 1]
                    });
                $("#jqxbutton_for_expandedIndexes").
                    jqxButton({
                        width: 300,
                    });
                $('#jqxbutton_for_expandedIndexes').
                    on('click', function () {
                        var value_of_expandedIndexes =
                            $('#jqx_Navigation_Bar').
                                jqxNavigationBar(
                                    'expandedIndexes');
                        $("#log").html(JSON.stringify(
                            value_of_expandedIndexes))
                    });
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/3c45c3d6d94e695afc55499c9fed6bdb.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm)**