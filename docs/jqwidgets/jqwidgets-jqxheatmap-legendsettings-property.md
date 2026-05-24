# jQWidgets jqxHeatMap legendSettings 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxheatmap-legendsettings-property/](https://www.geeksforgeeks.org/jqwidgets-jqxheatmap-legendsettings-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxHeatMap** 代表一个 jQuery 小部件，它显示了使用颜色编码来表示不同值的数据的图形表示。

**legendSettings 属性**用于设置或返回 legendSettings 属性。即该属性用于设置或返回热图图例的设置。它接受对象类型值，默认值为 null。

**语法:**

*   它用于设置 legendSettings 属性。

    ```html
    $('Selector').jqxHeatMap({ legendSettings : object });
    ```

*   它用于返回 legendSettings 属性。

    ```html
    var legendSettings = 
        $('Selector').jqxHeatMap('legendSettings');
    ```

**属性:**

*   **位置**:用于设置图例的位置。这些位置的可能选项是“顶部”、“底部”、“右侧”、“左侧”。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <script type = " text/JavaScript " src = " scripts/jquery-1 . 11 . 1min . js "></script><【script type = " text/JavaScript " src = " jqwidgets/jqxcore . js ">T10】

**示例:**下面的示例说明了 jQWidgets 中的 jqxHeatMap**legendSettings**属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxheatmap.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <h3>jQWidgets jqxHeatMap legendSettings property</h3>
        <body class='default'>
            <div id="heatmap"></div>
        </body>
    </center>
    <script type="text/javascript">
        $(document).ready(function () {
            var x = {
                labels: ['Ram', 'Rahul', 'Krishna']
            };
            var y = {
                labels: ['1st oct', '2nd oct', 
                         '3rd oct', '4th oct']
            };
            var arr = [
                [1, 3, 9, 5],
                [5, 3, 2, 3],
                [2, 0, 6, 8]
            ];
            $("#heatmap").jqxHeatMap({
                xAxis: x,
                yAxis: y,
                source: arr,
                title: 'Coding Questions Solved:',
                legendSettings: {
                    position: 'Left'
                }
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/ad0445041dca9a1f886928487cd9602c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxheatmap/jquery-heat map-入门. htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxheatmap/jquery-heatmap-getting-started.htm?search=)