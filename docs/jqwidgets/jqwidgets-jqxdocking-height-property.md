# jQWidgets jqxDocking 高度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdocking-height-property/](https://www.geeksforgeeks.org/jqwidgets-jqxdocking-height-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。****【jqxDocking】**用于表示一个小部件来管理多个窗口以及一个网页的布局。在这里，指定的 jqxDocking 中的每个窗口都可以执行多个任务，例如可以在网页上拖动、停靠到停靠区域、从停靠中移除、折叠到最小化状态以隐藏其内容，还可以展开以显示其内容。**

****高度** 属性用于设置或获取指定 jqxDocking 的高度。**

****语法:****

*   **用于设置*高度*属性:**

    ```html
    $('#jqxDocking').jqxDocking({height: 140});
    ```

*   **对于获得*高度**T2***属性:**

    ```html
    var height = $('#jqxDocking').jqxDocking('height');
    ```

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdocking . js”></脚本**

****示例:**下面的示例说明了 jQWidgets jqxDocking **高度**T4】属性。在下面的示例中，**高度** 属性的值已设置为 140。**

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
            src="jqwidgets/jqxdocking.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxwindow.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxDocking height Property
        </h3>
        <div id="jqx_Docking"
             style="margin: 25px;" 
             align="left">
            <div>
                <div id="Window">
                    <div>Window</div>
                    <div>
                        <h8>Content of the window</h8>
                        <ul>
                            <li>GFG</li>
                            <li>CSE</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        <input type="button" style="margin: 29px;" 
               id="jqxbutton_for_height" 
               value="Value of the height property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Docking").jqxDocking({
                    width: 250,
                    height: 140
                });
                $("#jqxbutton_for_height").
                    jqxButton({
                        width: 220
                    });
                $('#jqxbutton_for_height').on(
                    'click', function () {
                        var Value_of_height =
                            $('#jqx_Docking').jqxDocking(
                                'height');
                        $("#log").html(JSON.stringify(
                            Value_of_height));
                    });
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/a2d33e273c46144ce82fd51563f3ba03.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdocking/jquery-docking-api.htm)**