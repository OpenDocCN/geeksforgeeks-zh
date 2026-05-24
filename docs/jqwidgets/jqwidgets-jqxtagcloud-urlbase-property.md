# jQWidgets jqxTagCloud urlBase 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtagcloud-URL base-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-urlbase-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTagCloud** 用于显示一组用户生成的标签，这些标签与网站上的文章、帖子或视频相匹配。

***urlBase*** 属性用于设置或获取用于指定 **jqxTagCloud** 的所有标签的公共基础 URL 路径的字段名。

**语法:**

*   用于设置 *urlBase* 属性。

    ```html
    $('#jqxTagCloud').jqxTagCloud({ 
        urlBase: 'https://www.geeksforgeeks.org/' 
    });
    ```

*   获取 *urlBase* 属性。

    ```html
    var value = 
        $('#jqxTagCloud').jqxTagCloud({ 'urlBase' });
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”><

**示例:**下面的示例说明了 jQWidgets jqxTagCloud***urlBase***属性。在下面的示例中， ***urlBase*** 属性的值已设置为“https://www.geeksforgeeks.org/”。

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
            jQWidgets jqxTagCloud urlBase Property
        </h3>
        <div id="Tag_Cloud"></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_urlBase"
               value="Value of the urlBase property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                var Data_for_TagCloud = [
                    { Name: "GFG", Rating: 4 },
                    { Name: "is a", Rating: 3 },
                    { Name: "CS", Rating: 2 },
                    { Name: "Portal.", Rating: 5 }
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
                    urlBase: 'https://www.geeksforgeeks.org/'
                });
                $("#button_for_urlBase").
                    jqxButton({
                        width: 300
                    });
                $("#button_for_urlBase").jqxButton().
                click(function () {
                    var Value_of_urlBase =
                        $('#Tag_Cloud').jqxTagCloud('urlBase');
                    $("#log").html((Value_of_urlBase));
                });
            });
        </script>
    </center>
</body>
</html>
```

**输出:**

![](img/7d14f5ab5a907763734e239170b25ddb.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tag cloud-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm?search=)