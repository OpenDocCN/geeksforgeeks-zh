# jQWidgets jqxDataTable 显示聚合属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdatatable-show aggregations-property/](https://www.geeksforgeeks.org/jqwidgets-jqxdatatable-showaggregates-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxDataTable** 用于读取和显示 HTML 表格中的数据。这也用于显示来自各种数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**显示聚合**属性用于检查指定的 jqxDataTable 的聚合栏是否可见。该属性有两个可能的值，即“真”和“假”。

**语法:**

设置*显示聚合*属性:

```html
$('#dataTable').jqxDataTable({showAggregates: true});  
```

获取*显示聚合*属性:

```html
var showAggregates = 
    $('#dataTable').jqxDataTable('showAggregates'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>

**示例:**以下示例说明了 jQWidgets **显示聚合**属性。在下面的示例中，“显示聚合”属性的值被设置为“真”。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="
jqwidgets/styles/jqx.base.css" 
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
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxlistbox.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdropdownlist.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdatatable.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxDataTable 
            showAggregates Property
        </h3>
        <div id="#Data_Table"></div>
        <input type="button" style="margin: 29px;" 
               id="jqxbutton_for_showAggregates"
               value="Value of the showAggregates Property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#Data_Table").jqxDataTable({
                    showAggregates: true,
                    columns: [{
                        text: 'Employee_Name',
                        dataField: 'Employee_Name',
                        aggregates: ['count'],
                        width: 190
                    }, {
                        text: 'Company',
                        dataField: 'Company',
                        aggregates: ['count'],
                        width: 160
                    }, {
                        text: 'Designation',
                        dataField: 'Designation',
                        aggregates: ['count'],
                        width: 190
                    }]
                });
                $("#jqxbutton_for_showAggregates").
                    jqxButton({
                        width: 280
                    });
                $('#jqxbutton_for_showAggregates').
                    click(function () {
                        var value_of_showAggregates =
                            $('#Data_Table').
                                jqxDataTable(
                                    'showAggregates');
                        $("#log").html(JSON.stringify(
                            value_of_showAggregates))
                    });
            });
        </script>
        <table id="Data_Table" border="1">
            <thead>
                <tr>
                    <th>Employee_Name</th>
                    <th>Company</th>
                    <th>Designation</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Rohit</td>
                    <td>GeeksforGeeks</td>
                    <td>HR</td>
                </tr>
                <tr>
                    <td>Rahul</td>
                    <td>Capgemini</td>
                    <td>Software Engineer</td>
                </tr>
                <tr>
                    <td>Vivek</td>
                    <td>CESC</td>
                    <td>Electrical Engineer</td>
                </tr>
                <tr>
                    <td>Amit</td>
                    <td>Apple</td>
                    <td>Manager</td>
                </tr>
            </tbody>
        </table>
    </center>
</body>

</html>
```

**输出:**

![](img/2957c7632570ef64b0b258b1e63e7f66.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-api.htm)