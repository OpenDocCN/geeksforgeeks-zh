# jQWidgets jqxPopover 打开事件

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxpopover-open-event/](https://www.geeksforgeeks.org/jqwidgets-jqxpopover-open-event/)

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxPopover*** 是内容的小覆盖，用于在用户点击时显示任何元素的次要信息。

打开指定的 jqxPopover 小部件时，会触发**打开事件。**

****语法:****

```html
$('#jqxPopover').on('open', function () { // Code section });
```

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”/"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons . js”><**

****示例:**以下示例说明了 jQWidgets jqxPopover***open***事件。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css"
          type="text/css" />
    <script type="text/javascript" 
            src="scripts/jquery.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxpopover.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxPopover open Event
        </h3>
        <div id='jqx_Popover'>
            <center>
                GeeksforGeeks
            </center>
        </div>
        <input type="button" style="margin: 28px;" 
               id="button_for_Popover" 
               value="Toggle the Popover" />
        <input type="button" style="margin: 65px;" 
               id="button_for_open" 
               value="Open the above popover" />
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Popover").jqxPopover({
                    width: 180,
                    height: 80,
                    theme: 'energyblue',
                    autoClose: false,
                    selector: $("#button_for_Popover"),
                    title: 'Company_Name'
                });
                $("#button_for_Popover").jqxButton({
                    width: 200,
                    theme: 'energyblue'
                });
                $("#button_for_open").jqxButton({
                    width: 300,
                    theme: 'energyblue'
                });
                $('#button_for_open').jqxButton().
                    click(function () {
                        $('#jqx_Popover').jqxPopover(
                            'open');
                    })
                $('#jqx_Popover').on('open', function () {
                    $("#log").html('The Popover has been opened');
                })
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/263b92bd092bd5c380d5ea8c8750380c.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxpopover/jquery-popover-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxpopover/jquery-popover-api.htm?search=)**