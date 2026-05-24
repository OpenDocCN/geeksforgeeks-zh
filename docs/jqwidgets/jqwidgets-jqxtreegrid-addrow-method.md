# jQWidgets jqxTreeGrid addRow()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtreegrid-addrow-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtreegrid-addrow-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTreeGrid** 用于以树状结构表示数据。这个小部件对于显示分层数据的多列、数据分页、排序和筛选、数据编辑、列大小调整、固定列、条件格式、聚合和行选择非常有用。这些小部件还读取和显示来自任何类型数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

*addRow()* 方法用于在 jqxTreeGrid 的开头或结尾添加新行。

**语法:**

```html
$("#treeGrid").jqxTreeGrid('addRow', rowKey, {rowData}, rowPosition);
```

**参数:**该方法接受三个参数，如下所示:

*   **rowKey:** 这是唯一的 Id，将标识新添加的行。如果其值为空，那么 jqxTreeGrid 将创建一个唯一的密钥。
*   **行数据:**这是新行的数据。
*   **行位置:**这是新添加行的位置。它接受两个值，一个是“第一”，另一个是“最后”。它的默认值是“最后”。

**返回值:**此方法不返回值。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-treegrid-api.htm?search=) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>>

**示例:**下面的示例说明了 jQWidgets jqxTreeGrid*addRow()*方法。在下面的例子中，新的行被添加到树网格的末尾，并且这个新的行将在点击指定的按钮时继续添加。

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
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxTreeGrid addRow() Method
        </h3>
        <div id="jqxTreeGrid" style="margin: 25px;">
        </div>
        <input type="button" style="margin: 20px;" 
               id="button_for_addRow" 
               value="Add a new row at the end"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                var A = [{
                    "ID": 1,
                    "Employee_Name": "Amit",
                    "Company": "GeeksforGeeks",
                    "Designation": "Content Writer",
                    "expanded": true,
                    A1: [{
                        "ID": 2,
                        "Employee_Name": "Sumit",
                        "Company": "Amazon",
                        "Designation": "Software Engineer",
                    }, {
                        "ID": 3,
                        "Employee_Name": "Vivek",
                        "Company": "Apple",
                        "Designation": "Product Manager",
                        "expanded": true,
                        A1: [{
                            "ID": 4,
                            "Employee_Name": "Soni",
                            "Company": "Flipkart",
                            "Designation": "HR",
                        }]
                    }]
                }];

                var Data_Source = {
                    dataFields: [{
                        name: 'ID'
                    }, {
                        name: 'Employee_Name'
                    }, {
                        name: 'Company'
                    }, {
                        name: 'Designation'
                    }, {
                        name: 'A1',
                        type: 'array'
                    }, {
                        name: 'expanded'
                    }],
                    hierarchy: {
                        root: 'A1'
                    },
                    id: 'ID',
                    localData: A
                };

                var Data = new
                    $.jqx.dataAdapter(Data_Source);

                $("#jqxTreeGrid").jqxTreeGrid({
                    source: Data,
                    ready: function () {
                        $("#jqxTreeGrid").jqxTreeGrid(
                            'expandRow', '1');
                        $("#jqxTreeGrid").jqxTreeGrid(
                            'expandRow', '3');
                    },
                    columns: [{
                        text: 'Employee_Name',
                        align: 'center',
                        dataField: 'Employee_Name',
                        width: 140
                    }, {
                        text: 'Company',
                        align: 'center',
                        dataField: 'Company',
                        width: 150
                    }, {
                        text: 'Designation',
                        align: 'center',
                        dataField: 'Designation',
                        width: 150
                    }]

                });
                $("#button_for_addRow").jqxButton({
                    width: 300,
                    height: 35
                });
                $('#button_for_addRow').click(
                    function () {
                        $("#jqxTreeGrid").
                            jqxTreeGrid('addRow', 1, {
                                Employee_Name: "Raju",
                                Company: "TCS",
                                Designation: "Manager"
                            }, 'last');
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/d38fa555be76c453fe0e9486e294ce95.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-tree grid-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-treegrid-api.htm?search=)