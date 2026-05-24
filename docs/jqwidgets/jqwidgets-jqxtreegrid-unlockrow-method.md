# jQWidgets jqxTreeGrid unlock row()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtreegrid-unlock row-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtreegrid-unlockrow-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTreeGrid** 用于以树状结构表示数据。这个小部件对于显示分层数据的多列、数据分页、排序和筛选、数据编辑、列大小调整、固定列、条件格式、聚合和行选择非常有用。这些小部件还读取和显示来自任何类型数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**解锁行()**方法用于解锁指定 jqxTreeGrid 的锁定行。

**语法:**

```html
$("Selector").jqxTreeGrid('unlockRow', 'Row_Id');
```

**参数:**该方法接受如下所示的参数。

*   **Row_Id:** 这是将被解锁的指定锁定行。

**返回值:**此方法不返回值。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>>

**示例:**下面的示例说明了 jQWidgets jqxTreeGrid**unlock row()**方法。在下面的示例中，第 3 行已经被锁定，因此此方法解锁了该行。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
"jqwidgets/styles/jqx.base.css" type="text/css"/>
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
    <script type="text/javascript" 
            src="jqwidgets/jqxtreegrid.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxTreeGrid unlockRow() Method
        </h3>
        <div id="jqxTreeGrid" style="margin: 25px;">
        </div>
        <input type="button" style="margin: 25px;" 
               id="button_for_unlockRow" 
               value="Unlock the above locked row"/>
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
                    },
                    ready: function () {
                        $("#jqxTreeGrid").jqxTreeGrid(
                          'expandRow', '3');
                    },
                    columns: [{
                        text: 'Employee_Name',
                        dataField: 'Employee_Name',
                        width: 140
                    }, {
                        text: 'Company',
                        dataField: 'Company',
                        width: 130
                    }, {
                        text: 'Designation',
                        dataField: 'Designation',
                        width: 150
                    }]

                });
                $("#button_for_unlockRow").jqxButton({
                    width: 220
                });
                $("#jqxTreeGrid").jqxTreeGrid(
                  'lockRow', 3);
                $('#button_for_unlockRow').click(
                  function () {
                    $("#jqxTreeGrid").jqxTreeGrid(
                      'unlockRow', 3);
                });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/741d4b76c225c75ae7fb5f9fe91935d2.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-tree grid-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-treegrid-api.htm?search=)