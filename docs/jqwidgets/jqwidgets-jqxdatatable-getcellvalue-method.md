# jQWidgets jqxDataTable getCellValue()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdatatable-getcellvalue-method/](https://www.geeksforgeeks.org/jqwidgets-jqxdatatable-getcellvalue-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxDataTable** 用于读取和显示 HTML 表格中的数据。这也用于显示来自各种数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**getCellValue()** 方法用于返回特定指定单元格的值。

**语法:**

```html
$("#dataTable").jqxDataTable('getCellValue', rowIndex, dataField);
```

**参数:**该方法接受两个参数，如下图所示。

*   **行索引:**指定要返回单元格值的行索引。
*   **数据字段:**指定要返回单元格值的数据字段。

**返回值:**该方法返回指定单元格的值。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>

**示例:**下面的示例说明了 jQWidgets **getCellValue()** 方法。在下面的示例中，第三行的指定将作为单元格值返回。

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
        <h1 style="color: green;"> 
          GeeksforGeeks 
        </h1>
        <h3> 
          jQWidgets jqxDataTable getCellValue() Method 
        </h3>
        <div id="Data_Table"></div>
        <input type="button" style="margin: 31px;" 
               id="jqxbutton" 
               value="Invoke the getCellValue() Method" />
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
                theme: 'energyblue',
                source: data_Adapter,
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
                var Selected_cellValue = 
                         $("#Data_Table").
                    jqxDataTable('getCellValue', 
                                 2, 'Designation');
                $("#log").html(JSON.stringify(
                               Selected_cellValue))
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/7a4aa4ee28a1384a4c29cea48c276a85.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-api.htm?search=)