# jQWidgets jqxTagCloud 显示值属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtagcloud-display value-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-displayvalue-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTagCloud** 用于显示一组用户生成的标签，这些标签与网站上的文章、帖子或视频相匹配。每个标签都有一个权重值，该值对应于其在页面上的受欢迎程度、重要性或重复度。云中的关键字可以包含它们自己的网址，该网址导航到与相关标签相关联的项目集合。

**displayValue****属性用于设置或获取 display value 属性，该属性用于指定是否为指定的 jqxTagCloud 在文本后添加标记值字段。它接受布尔类型值&其默认值为假。**

****语法:****

*   **用于设置*显示值*属性。

    ```html
    $('#jqxTagCloud').jqxTagCloud({ displayValue: true });
    ```** 
*   **用于获取*显示值*属性。

    ```html
    var value = $('#jqxTagCloud').jqxTagCloud({ 'displayValue' });
    ```** 

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”><**

****示例:**以下示例说明了 jQWidgets jqxTagCloud**display value**属性。在以下示例中，**显示值** 属性的值已设置为真。**

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
            jQWidgets jqxTagCloud displayValue Property
        </h3>
        <div id="Tag_Cloud"></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_displayValue"
          value="Value of the displayValue property"/>
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
                    displayValue: true
                });
                $("#button_for_displayValue").
                    jqxButton({
                        width: 300
                    });
                $("#button_for_displayValue").jqxButton().
                    click(function () {
                        var Value_of_displayValue =
                            $('#Tag_Cloud').jqxTagCloud(
                                'displayValue');
                        $("#log").html((
                            Value_of_displayValue));
                    });
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/da96ad97ebf33e94b4090a673cfb6b98.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tag cloud-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm?search=)**