# jQWidgets jqxGrid enablekeyboarddelete 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxgrid-enablekeyboarddelete-property/](https://www.geeksforgeeks.org/jqwidgets-jqxgrid-enablekeyboarddelete-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxGrid 用于说明以表格形式显示数据的 jQuery 小部件。此外，它完全支持与数据的连接，以及分页、分组、排序、过滤和编辑。

**enablekeyboarddelete 属性**用于通过键盘的 *delete* 键启用或禁用单元格或行值的删除。仅当可编辑属性值设置为 true 时，此属性才有效。这里，用户必须选择一行或一个单元格，以便使用键盘的删除键将其删除。它是布尔类型，缺省值为真。

**语法:**

*   设置**启用键盘删除**属性。

    ```html
    $('#Selector').jqxGrid({ enablekeyboarddelete: false});
    ```

*   返回**启用键盘删除**属性。

    ```html
    var enablekeyboarddelete = 
        $('#Selector').jqxGrid('enablekeyboarddelete');
    ```

**链接文件:**从给定链接下载 https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery-1 . 11 . 1 . min . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata

下面的例子说明了 jQWidgets 中的 jqxGrid enablekeyboarddelete 属性。

**示例:**

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
            src="jqwidgets/jqxdata.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxmenu.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxgrid.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxgrid.selection.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxGrid enablekeyboarddelete property

        </h3>
        <br />

        <div id="jqxg"></div>

    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var d = new Array();
            var subjectNames =
                ["C++", "Scala", "Java", "C", "R", "JavaScript"];

            var pageNumber =
                ["7", "8", "12", "11", "10", "19"];

            for (var j = 0; j < 50; j++) {
                var r = {};
                r["subjectnames"] =
                    subjectNames[Math.floor(
                        Math.random() * subjectNames.length)
                    ];

                r["pagenumber"] =
                    pageNumber[Math.floor(
                        Math.random() * pageNumber.length)
                    ];
                d[j] = r;

            }
            var src = {
                localdata: d,
                datatype: "array",
            };
            var data_Adapter = new $.jqx.dataAdapter(src);
            $("#jqxg").jqxGrid({
                source: data_Adapter,
                filterable: true,
                theme: 'energyblue',
                height: "260px",
                selectionmode: 'singlecell',
                width: "280px",
                editable: true,
                enablekeyboarddelete: true,
                columns: [
                    {
                        text: "Subject Name",
                        datafield: "subjectnames",
                        width: "140px",
                    },
                    {
                        text: "Page No.",
                        datafield: "pagenumber",
                        width: "140px",
                    },
                ],
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/e6d9c84dfcb345b876a1eb2b99b13c5b.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxgrid/jquery-grid-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxgrid/jquery-grid-api.htm?search=)