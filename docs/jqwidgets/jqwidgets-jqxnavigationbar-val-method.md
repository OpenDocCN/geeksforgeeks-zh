# jQWidgets jqxNavigationBar val()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnavigationbar-val-method/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-val-method/)

***jQWidgets*** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxNavigationBar*** 用于表示具有标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

***val()*** 方法用于设置或获取指定 jqxNavigationBar 的展开项。

**语法:**

*   要设置展开的项目:

    ```html
    $('Selector').jqxNavigationBar('val', Item_Index);
    ```

*   对于使用 jQuery 的 val()设置扩展项:

    ```html
    $("Selector").val(Item_Index);
    ```

*   要获取展开的项目:

    ```html
    var value = $("Selector").jqxNavigationBar('val');
    ```

*   要使用 jQuery 的 val()获取扩展项的索引:

    ```html
    var value = $("Selector").val();
    ```

**参数:**该方法接受如下所示的参数:

*   **Item_Index:** 这是项目的指定索引。

**返回值:**该方法返回项目的索引。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxexpander . js”><

**示例:**下面的示例说明了 jQWidgets jqxNavigationBar**val()**方法。

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
            jQWidgets jqxNavigationBar val() Method
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
               id="jqxbutton_for_val" 
               value="Set and get the 0th expanded item"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 290,
                        height: 150,
                    });
                $("#jqxbutton_for_val").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_val').
                    on('click', function () {
                        var Item_Index = 0;

                        // Setting the expanded item
                        $('#jqx_Navigation_Bar').
                        jqxNavigationBar('val',
                            Item_Index);

                        // Getting the expanded item
                        var a = $('#jqx_Navigation_Bar').
                            jqxNavigationBar('val');
                        $("#log").html(JSON.stringify(a))
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/7a7f92a390e34d54a61748702af9321f.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm?search=)