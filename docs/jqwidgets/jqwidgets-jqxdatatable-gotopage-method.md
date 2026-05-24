# jQWidgets jqxDataTable goToPage()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdatatable-goto page-method/](https://www.geeksforgeeks.org/jqwidgets-jqxdatatable-gotopage-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxDataTable** 用于读取和显示 HTML 表格中的数据。这也用于显示来自各种数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**goToPage()** 方法用于导航到特定的指定页面。只有当可分页属性设置为*真*时，这才是可能的。

**语法:**

```html
$("#dataTable").jqxDataTable('goToPage', pageIndex);
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>

下面的例子说明了 jQWidgets **goToPage()** 方法。

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
        <h1 style="color: green;"> 
          GeeksforGeeks 
        </h1>
        <h3> 
          jQWidgets jqxDataTable goToPage() Method 
        </h3>
        <div id="Data_Table"></div>
        <input type="button" style="margin: 31px;" 
               id="jqxbutton" 
               value="Go to the second page" />
    </center>
    <script>
        $(document).ready(function () {
            var Data = new Array();
            var Employee_Name = [
                "Ravi", "Sumit", "Amit",
                "Aakash", "Vivek",
                "Sagar", "Shiva", "Soni",
                "Rahul", "Deepak",
                "Shubham", "Shoham"];
            var Company = [
                "GeeksforGeeks", "Amazon",
                "Google", "Facebook",
                "GeeksforGeeks", "TCS", 
                "CTS", "Wipro",
                "Apple", "Capgemini",
                "OLA", "Zomato"];
            var Designation = [
                "Content Writer", "Software Engineer",
                "Data Analyst",
                "Data Scientist", "HR", "CEO", 
                "Director", "Manager",
                "Founder", "Co-founder", 
                "Content Reviewer",
                "Content Manager"];

            a = 0;
            while (a < 12) {
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
                width: 550,
                theme: 'energyblue',
                pageable: true,
                source: data_Adapter,
                columns: [{
                    text: 'Employee_Name',
                    dataField: 'Employee_Name',
                    width: 200
                }, {
                    text: 'Company',
                    dataField: 'Company',
                    width: 160
                }, {
                    text: 'Designation',
                    dataField: 'Designation',
                    width: 190
                }]
            });
            $("#jqxbutton").jqxButton({
                theme: 'energyblue',
                width: 210,
                height: 35
            });
            $('#jqxbutton').click(function () {
                $("#Data_Table").jqxDataTable(
                  'goToPage', 2);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/7748174050f0021dfb14edd390010c39.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdatatable/jquery-datatable-api.htm?search=)