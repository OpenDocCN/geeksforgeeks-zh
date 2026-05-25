# jqwidgets jqxtagcloud item click event

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-itemclick-event/](https://www.geeksforgeeks.org/jqwidgets-jqxtagcloud-itemclick-event/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxTagCloud` 用于显示一组用户生成的标签，这些标签与网站上的文章、帖子或视频相匹配。

当点击指定 `jqxTagCloud` 的标签元素时，触发 `itemClick` 事件。此事件接受如下所示的一些参数:
*   `label`: 这是物品的标签。
*   `value`: 这是物品的值。
*   `url`: 这是项目的 url。
*   `visibleIndex`: 这是项目的可见索引。
*   `index`: 这是项目的索引。
*   `originalEvent`: 这是点击事件对象。
*   `target`: 这是项目的 HTML 元素。

**语法:**

```javascript
$('#Tag_Cloud').on('itemClick', function(event)
   {
       var args = event.args;
       $("#log").html("The item has been clicked.");
   });
```

**链接文件:** 从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
<script type="text/javascript" src="scripts/jquery.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxdata.js"></script>
```

**示例:** 下面的示例说明了 `jQWidgets` `jqxTagCloud` 的 `itemClick` 事件。

## HTML

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
            jQWidgets jqxTagCloud itemClick Event
        </h3>
        <div id="Tag_Cloud"></div>
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
                    valueMember: 'Rating'
                });
                $('#Tag_Cloud').on('itemClick', 
                                function (event) {
                    var args = event.args;
                    $("#log").html(
                    "The item has been clicked.");
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/1f95187155ee983c1470930a4f30e8eb.png)

**参考:** [https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtagcloud/jquery-tagcloud-api.htm?search=)