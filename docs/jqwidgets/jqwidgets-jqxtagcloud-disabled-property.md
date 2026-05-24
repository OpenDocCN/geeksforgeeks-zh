# jQWidgets jqxTagCloud 禁用属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtagcloud-disabled-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-disabled-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTagCloud** 用于显示一组用户生成的标签，这些标签与网站上的文章、帖子或视频相匹配。

**禁用属性**用于启用或禁用跟踪指定 jqxTagCloud 的标签链接的能力。此属性接受“真”和“假”两个值。

**语法:**

*   要设置*禁用的*属性:

    ```html
    $('#jqxTagCloud').jqxTagCloud({ disabled: true });
    ```

*   要禁用*属性:*

    ```html
    *var disabled = $('#jqxTagCloud').jqxTagCloud('disabled');*
    ```

***链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。*

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> *<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”><*

***示例:**以下示例说明了 jQWidgets jqxTagCloud **禁用属性**。在下面的例子中，*禁用的*属性的值被设置为真。*

## *超文本标记语言*

```html
*<!DOCTYPE html>
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
            src="jqwidgets/jqxdata.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxtagcloud.js">
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
            jQWidgets jqxTagCloud disabled Property
        </h3>
        <div id="Tag_Cloud"></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_disabled" 
               value="Value of the disabled property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                var Data_for_TagCloud = [
                    { Name: "GFG", Rating: 4 },
                    { Name: "is a", Rating: 3 },
                    { Name: "CS", Rating: 2 },
                    { Name: "Portal.", Rating: 5 },
                ];
                var dataAdapter = new
                    $.jqx.dataAdapter({
                        localData: Data_for_TagCloud
                    });
                $('#Tag_Cloud').jqxTagCloud({
                    width: 450,
                    source: dataAdapter,
                    displayMember: 'Name',
                    valueMember: 'Rating',
                    disabled: true
                });
                $("#button_for_disabled").
                    jqxButton({
                        width: 300
                    });
                $("#button_for_disabled").jqxButton().
                    click(function () {
                        var Value_of_disabled =
                        $('#Tag_Cloud').jqxTagCloud(
                                'disabled');
                        $("#log").html((
                            Value_of_disabled));
                    });
            });
        </script>
    </center>
</body>

</html>*
```

***输出:***

*![](img/590506787951abbd349f493422296e33.png)*

***参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tag cloud-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm)*