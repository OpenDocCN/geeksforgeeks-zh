# jQWidgets jqxGrid 滚动模式属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxgrid-scroll mode-property/](https://www.geeksforgeeks.org/jqwidgets-jqxgrid-scrollmode-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxGrid** 用于说明以表格形式显示数据的 jQuery 小部件。此外，它完全支持与数据的连接，以及分页、分组、排序、过滤和编辑。

**滚动模式属性**用于设置或获取显示的 jqxGrid 的滚动模式。它属于字符串类型，默认情况下其值为默认值。

滚动的可能模式如下:

*   **默认:**是规定的滚动默认模式。
*   **逻辑:**是滚动条滑块的运动是通过行的方式，而不是通过像素的方式的逻辑模式。
*   **延迟:**这是所述的延迟模式，其中每当用户拉动滚动条的拇指时，内容就不动。

**语法:**

*   设置*滚动模式*属性。

    ```html
    $('#Selector').jqxGrid({ scrollmode: 'logical'});
    ```

*   返回*滚动模式*属性。

    ```html
    var scrollmode = $('#Selector').jqxGrid('scrollmode');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxdata

下面的例子说明了 jQWidgets 中的 jqxGrid **scrollmode 属性**。

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

        <h3>jQWidgets jqxGrid scrollmode
            property
        </h3>
        <br />

        <div id="jqxg"></div>

        <div>
            <input type="button" id="jqxBtn" 
                   style="margin-top: 25px" 
                   value="Click here" />
        </div>

        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            var d = new Array();
            var subjectNames =
                ["C++", "Scala", "Java", 
                 "C", "R", "JavaScript"];

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
                sortable: true,
                theme: 'energyblue',
                scrollmode: 'deferred',
                height: "260px",
                width: "260px",
                columns: [
                    {
                        text: "Subject Name",
                        datafield: "subjectnames",
                        width: "120px",
                    },
                    {
                        text: "Page No.",
                        datafield: "pagenumber",
                        width: "120px",
                    },
                ],
            });

            $("#jqxBtn").jqxButton({
                width: "180px",
                height: "30px",
            });
            $("#jqxBtn").on("click", function () {
                var sm = $('#jqxg').jqxGrid('scrollmode');
                $('#log').text("Mode of scrolling: " + sm);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/468dfbe57e8f33766245a6b446084bf5.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxgrid/jquery-grid-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxgrid/jquery-grid-api.htm)