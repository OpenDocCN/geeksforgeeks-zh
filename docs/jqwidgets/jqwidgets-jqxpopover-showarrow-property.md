# jQWidgets jqxPopover show arrow 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxpopover-show arrow-property/](https://www.geeksforgeeks.org/jqwidgets-jqxpopover-showarrow-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。****jqxPopover**是内容的小覆盖，用于在用户点击时显示任何元素的次要信息。**

****显示箭头** **属性**用于设置或获取指定 jqxPopover 小部件的箭头是否显示。**

****语法:****

*   **设置*显示箭头*属性:**

    ```html
    $('#jqxPopover').jqxPopover({showArrow: true});
    ```

*   **获取*显示箭头*属性:**

    ```html
    var arrowOffsetValue = 
        $('#jqxPopover').jqxPopover('showArrow');
    ```

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”/"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons . js”><**

****示例:**下面的示例说明了 jQWidgets jqxPopover***showArrow***属性。在下面的例子中， ***显示箭头*** 属性的值被设置为真。**

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
            jQWidgets jqxPopover showArrow Property
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
               id="button_for_showArrow"
           value="Value of the showArrow property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Popover").jqxPopover({
                    width: 180,
                    height: 80,
                    theme: 'energyblue',
                    autoClose: false,
                    showArrow: true,
                    selector: $("#button_for_Popover"),
                    title: 'Company_Name'
                });
                $("#button_for_Popover").jqxButton({
                    width: 200,
                    theme: 'energyblue'
                });
                $("#button_for_showArrow").jqxButton({
                    width: 300,
                    theme: 'energyblue'
                });
                $('#button_for_showArrow').jqxButton().
                     click(function () {
                    var Value_of_showArrow =
                        $('#jqx_Popover').jqxPopover(
                          'showArrow');
                    $("#log").html((Value_of_showArrow));
                })
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/ea39f1c6a08b2ff98920f8e49726f930.png)**

****参考:**[**https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxpopover/jquery-popover-API . htm**](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxpopover/jquery-popover-api.htm)**