# jQWidgets jqxDataTable getSelection()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdatatable-get selection-method/](https://www.geeksforgeeks.org/jqwidgets-jqxdatatable-getselection-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxDataTable** 用于读取和显示 HTML 表格中的数据。这也用于显示来自各种数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**getSelection()** 方法用于返回选中行的列表。

**语法:**

```html
$("#dataTable").jqxDataTable('getSelection');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>

下面的例子说明了 jQWidgets **getSelection()** 方法。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
    "jqwidgets/styles/jqx.base.css" type="text/css" />
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
        <h1 style="color:green;"> 
          GeeksforGeeks 
        </h1>
        <h3> 
          jQWidgets jqxDataTable getSelection() Method 
        </h3>
        <div id="Data_Table"></div>
        <input type="button" style="margin: 31px;" 
               id="jqxbutton" 
               value="Invoke the getSelection() Method" />
        <div id="log"></div>
    </center>
    <script>
        $(document).ready(function () {
            var Data = new Array();
            var Employee_Name = [
                "Ravi", "Sumit", "Amit", 
                "Aakash", "Vivek"];
            var Company = [
                "GeeksforGeeks", "Amazon", 
                "Google", "Facebook",
                "GeeksforGeeks"];
            var Designation = [
                "Content Writer", "Software Engineer", 
                "Data Analyst",
                "Data Scientist", "HR"];

            a = 0;
            while (a < 5) {
                var row = {};
                row["Employee_Name"] = Employee_Name[a];
                row["Company"] = Company[a];
                row["Designation"] = Designation[a]
                Data[a] = row;
                a++;
            }

            var Data_Source = {
                localData: Data,
                dataType: "array",
                dataFields: [{
                    name: 'Employee_Name',
                    type: 'string'
                }, {
                    name: 'Company',
                    type: 'string'
                }, {
                    name: 'Designation',
                    type: 'string'
                }]
            };
            var data_Adapter = 
                new $.jqx.dataAdapter(Data_Source);
            $("#Data_Table").jqxDataTable({
                width: 560,
                editable: true,
                theme: 'energyblue',
                source: data_Adapter,
                ready: function () {
                    $("#Data_Table").jqxDataTable(
                                    'selectRow', 2);
                },
                columns: [{
                    text: 'Employee_Name',
                    dataField: 'Employee_Name',
                    width: 210
                }, {
                    text: 'Company',
                    dataField: 'Company',
                    width: 150
                }, {
                    text: 'Designation',
                    dataField: 'Designation',
                    width: 200
                }]
            });
            $("#jqxbutton").jqxButton({
                theme: 'energyblue',
                width: 250
            });
            $('#jqxbutton').click(function () {
                var selected_row = $("#Data_Table").
                          jqxDataTable('getSelection');
                b = 0;
                while (b < selected_row.length) {
                    var data = selected_row[b];
                    b++;
                }
                $("#log").html(JSON.stringify(data))
            });
        });
    </script>
</body>
</html>
```

**输出:**

![](img/52ebbbdcddd3753a202463a2c7739ba1.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-api.htm?search=)