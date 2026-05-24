# jQWidgets jqxTreeGrid getCheckedRows()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtreegrid-getcheckedrows-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtreegrid-getcheckedrows-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTreeGrid** 用于以树状结构表示数据。这个小部件对于显示分层数据的多列、数据分页、排序和筛选、数据编辑、列大小调整、固定列、条件格式、聚合和行选择非常有用。这些小部件还读取和显示来自任何类型数据源的数据，如 XML、JSON、Array、CSV 或 TSV。

**getCheckedRows()** 方法用于返回指定 jqxTreeGrid 的所有选中行的平面数组。

有一些保留的行成员:

*   **勾选:**这是布尔值。这里，返回该行的选中状态。
*   **展开:**这是布尔值。这里，返回行的展开状态。
*   **图标:**这是字符串值。这里，返回该行的图标网址。
*   **leaf:** 这是布尔值。这里，返回层次结构中行的叶的存在。
*   **级别:**这是整数值。这里，返回行的层次级别。
*   **父级:**这是对象。它为根行返回 null，否则返回父行的对象。
*   **记录:**这是一个数组。这里，返回该行的子行集合。
*   **选中:**这是布尔值。这里，返回行的选定状态。
*   **uid:** 这可以是数字或字符串值。这里，返回行的唯一标识或键。

**语法:**

```html
$('Selector').jqxTreeGrid('getCheckedRows');
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回所有选中行的平面数组

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxdata . js”>>

**示例:**下面的示例说明了 jQWidgets jqxTreeGrid**getCheckedRows()**方法。在下面的示例中，返回选中的第一行和第三行。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css"
          type="text/css" />
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
      <h1 style="color: green">GeeksforGeeks</h1>
      <h3>jQWidgets jqxTreeGrid getCheckedRows() Method</h3>
      <div id="jqxTreeGrid" style="margin: 25px"></div>
      <input
        type="button"
        style="margin: 20px"
        id="button_for_getCheckedRows"
        value="Get the checked rows" />
      <div id="log"></div>

      <script type="text/javascript">
        $(document).ready(function () {
          var A = [
            {
              ID: 1,
              Employee_Name: "Amit",
              Company: "GeeksforGeeks",
              Designation: "Content Writer",
              expanded: true,
              A1: [
                {
                  ID: 2,
                  Employee_Name: "Sumit",
                  Company: "Amazon",
                  Designation: "Software Engineer",
                },
                {
                  ID: 3,
                  Employee_Name: "Vivek",
                  Company: "Apple",
                  Designation: "Product Manager",
                  expanded: true,
                  A1: [
                    {
                      ID: 4,
                      Employee_Name: "Soni",
                      Company: "Flipkart",
                      Designation: "HR",
                    },
                  ],
                },
              ],
            },
          ];

          var Data_Source = {
            dataFields: [
              {
                name: "ID",
              },
              {
                name: "Employee_Name",
              },
              {
                name: "Company",
              },
              {
                name: "Designation",
              },
              {
                name: "A1",
                type: "array",
              },
              {
                name: "expanded",
              },
            ],
            hierarchy: {
              root: "A1",
            },
            id: "ID",
            localData: A,
          };

          var Data = new $.jqx.dataAdapter(Data_Source);

          $("#jqxTreeGrid").jqxTreeGrid({
            source: Data,
            editable: true,
            checkboxes: true,
            ready: function () {
              $("#jqxTreeGrid").jqxTreeGrid("expandRow", "1");
              $("#jqxTreeGrid").jqxTreeGrid("expandRow", "3");
            },
            columns: [
              {
                text: "Employee_Name",
                align: "center",
                dataField: "Employee_Name",
                width: 140,
              },
              {
                text: "Company",
                align: "center",
                dataField: "Company",
                width: 150,
              },
              {
                text: "Designation",
                align: "center",
                dataField: "Designation",
                width: 150,
              },
            ],
          });
          $("#button_for_getCheckedRows").jqxButton({
            width: 300,
            height: 35,
          });
          $("#jqxTreeGrid").jqxTreeGrid("checkRow", 1);
          $("#jqxTreeGrid").jqxTreeGrid("checkRow", 3);
          $("#button_for_getCheckedRows").click(function () {
            var checked_Rows = $("#jqxTreeGrid")
              .jqxTreeGrid("getCheckedRows");
            var checked_Rows_Data = "";
            var a = 0;
            while (a < checked_Rows.length) {
              checked_Rows_Data +=
                checked_Rows[a].Employee_Name +
                " " +
                checked_Rows[a].Company +
                " " +
                checked_Rows[a].Designation +
                " & ";
              a++;
            }

            $("#log").html(JSON.stringify(checked_Rows_Data));
          });
        });
      </script>
    </center>
  </body>
</html>
```

**输出:**

![](img/e79c61fccb240dabcb44e0157729d377.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-tree grid-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtreegrid/jquery-treegrid-api.htm?search=)