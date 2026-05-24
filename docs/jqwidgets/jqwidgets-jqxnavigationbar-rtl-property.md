# jqwidgets jqxn 可导航 rtl 属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxnavigationbar-RTL-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-rtl-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。****jqxNavigationBar**用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。**

******【RTL】****属性用于检查指定的 jqxNavigationBar 是否启用了从右向左支持。此属性接受“真”和“假”两个值。******

********语法:********

*   ****设置 *rtl* 属性:****

    ```html
    **$("Selector").jqxNavigationBar({ rtl: false });** 
    ```

*   ****获得 *rtl* 房产:****

    ```html
    **var rtl = $('Selector').jqxNavigationBar('rtl');**
    ```

******链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。****

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> ****<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><****

******示例:**以下示例说明了 jQWidgets jqxNavigationBar**RTL 房产**。在下面的示例中， **rtl** 属性的值被设置为 false。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
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
            jQWidgets jqxNavigationBar rtl Property
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
               id="jqxbutton_for_rtl" 
               value="Value of the rtl property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 132,
                        rtl: false
                    });
                $("#jqxbutton_for_rtl").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_rtl').
                    on('click', function () {
                        var value_of_rtl =
                            $('#jqx_Navigation_Bar').
                                jqxNavigationBar(
                                    'rtl');
                        $("#log").html(JSON.stringify(
                            value_of_rtl))
                    });
            });
        </script>
    </center>
</body>

</html>**
```

******输出:******

****![](img/7fb635a456945c9389282031063c9cd2.png)****

******参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm)****