# jqwidgets jqxtagcloud hideitem()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtagcloud-hide item-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-hideitem-method/)

**jQWidgets****是一个为 PC 和移动设备制作基于 web 的应用的 JavaScript 框架。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 ***jqxTagCloud*** 小部件用于显示一组用户生成的标签，这些标签与网站上的文章、帖子或视频相匹配。**

*****隐藏项()*** 方法用于隐藏具有指定 **jqxTagCloud** 的特定索引的元素。**

****语法:****

```html
$('#jqxTagCloud').jqxTagCloud('hideItem', index);
```

****参数:**该方法接受如下所示的参数。**

*   ****索引:**这是其项目将被隐藏的索引。**

****返回值:**此方法不返回值。**

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”><**

****示例:**下面的示例说明了 jQWidgets***hide item()***的方法。在下面的示例中，具有第一个索引的项目被隐藏。**

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
            jQWidgets jqxTagCloud hideItem() Method
        </h3>
        <div id="Tag_Cloud"></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_hideItem" 
               value="Hide the 1st index item"/>
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
                    valueMember: 'Rating'
                });
                $("#button_for_hideItem").
                    jqxButton({
                        width: 250
                    });
                $("#button_for_hideItem").jqxButton().
                    click(function () {
                        $('#Tag_Cloud').jqxTagCloud(
                            'hideItem', 1);
                    });
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/975aabb40cd53ead001c1fd7dddca32e.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tag cloud-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm?search=)**