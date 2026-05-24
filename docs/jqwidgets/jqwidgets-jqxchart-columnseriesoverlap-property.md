# jQWidgets jqxChart columns series overlap 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxchart-columnseriesoverlap-property/](https://www.geeksforgeeks.org/jqwidgets-jqxchart-columnseriesoverlap-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxChart** 是一个轻量级且功能强大的图表小部件，100%用 javascript 编写。它提供了许多高级功能，并支持三种不同的渲染技术——SVG、HTML5 画布& VML。

**columns series overlap 属性**用于设置或返回 columns series overlap 属性。即该属性用于启用或禁用列序列的重叠。它接受布尔类型值，默认值为 false。

**语法:**

*   设置 **columnSeriesOverlap** 属性。

    ```html
    $('Selector').jqxChart({ 
        columnSeriesOverlap : boolean 
    });
    ```

*   返回 **columnSeriesOverlap** 属性。

    ```html
    var columnSeriesOverlap = $('Selector')
            .jqxChart('columnSeriesOverlap');
    ```

**链接文件:**从链接下载 https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> 脚本类型=【text/JavaScript】src =【jqwidgets/jqxchart . core

**示例:**下面的示例说明了 jQWidgets 中的 jqxHeatMap columnSeriesOverlap 属性:

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
              src="jqwidgets/jqxchart.core.js">
    </script>
    <script type="text/javascript" 
              src="jqwidgets/jqxdraw.js">
    </script>
    <script type="text/javascript" 
              src="jqwidgets/jqxdata.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <h3>jQWidgets jqxChart columnSeriesOverlap property</h3>
        <body class='default'></body>
        <div id='chartContainer' 
             style="width:700px; height: 500px"/>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var Data = [{
            name: 'A',
            ques: 1,
        }, {
            name: 'B',
            ques: 1,
        }, {
            name: 'C',
            ques: 3,
        }, {
            name: 'D',
            ques: 21,
        }];
        // prepare jqxChart settings
        var settings = {
            showLegend: true,
            enableCrosshairs: true,
            columnSeriesOverlap: true,
            title: "Coding Questions",
            description: "Solved Daily",
            source: Data,
            categoryAxis: {
                dataField: 'name'
            },
            seriesGroups: [{
                type: 'line',
                orientation: 'horizontal',
                columnsGapPercent: 10,
            valueAxis: {
                unitInterval: 10,
                maxValue: 15,
                displayValueAxis: true,
                description: '',
            },
            series: [{
                dataField: 'ques',
                displayText: 'Question Solved'
            }]
        }]
        };
        $('#chartContainer').jqxChart(settings);
    });

    </script>

</body>

</html>
```

**输出:**

![](img/7f7c306e4b83b8f977a4e0d5a7ce5930.png)

**参考:**[**https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxchart/jquery-chart-API . htm？搜索=**](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxchart/jquery-chart-api.htm?search=)