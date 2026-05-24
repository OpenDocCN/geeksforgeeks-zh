# jQWidgets jqxDocking rtl 物业

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxdocking-RTL-property/](https://www.geeksforgeeks.org/jqwidgets-jqxdocking-rtl-property/)

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxDocking*** 用于表示一个小部件来管理多个窗口以及一个网页的布局。在这里，指定的 jqxDocking 中的每个窗口都可以执行多个任务，例如可以在网页上拖动、停靠到停靠区域、从停靠中移除、折叠到最小化状态以隐藏其内容，还可以展开以显示其内容。

***【RTL】***属性用于设置或获取指定 jqxDocking 的元素是否与从右向左的字体对齐。

**语法:**

*   用于设置 ***rtl*** 属性:

```html
$('#jqxDocking').jqxDocking({rtl : true});  
```

*   对于获得 ***rtl*** 房产:

```html
var rtl = $('#jqxDocking').jqxDocking('rtl'); 
```

**链接文件:**从给定链接下载https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdocking . js”><

**示例:**以下示例说明了 jQWidgets ***rtl*** 属性。在以下示例中， ***rtl*** 属性的值已设置为 true。

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
            src="jqwidgets/jqxdocking.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxDocking rtl Property
        </h3>
        <div id="jqx_Docking" style="margin: 25px;" 
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
               id="jqxbutton_for_rtl" 
               value="Value of the rtl property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Docking").jqxDocking({
                    width: 250,
                    rtl: true
                });
                $("#jqxbutton_for_rtl").
                    jqxButton({
                        width: 250
                    });
                $('#jqxbutton_for_rtl').on(
                    'click', function () {
                        var Value_of_rtl =
                        $('#jqx_Docking').jqxDocking(
                                'rtl');
                        $("#log").html(JSON.stringify(
                            Value_of_rtl));
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/5d2bc5596d6479441353c41804b8ced4.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdocking/jquery-docking-api.htm?search=)