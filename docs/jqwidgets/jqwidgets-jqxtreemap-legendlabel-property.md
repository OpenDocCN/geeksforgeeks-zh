# jqwidgets jqxtree map legladelbel 性质

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtreemap-legendlabel-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtreemap-legendlabel-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxTreeMap** 用于显示嵌套矩形的层次数据集。树的每个分支都表示为一个矩形，然后用代表子分支的更小的矩形平铺显示。这里，叶节点的矩形具有与数据上的指定维度成比例的面积。

**图例标签属性**用于为指定的 jqxTreeMap 设置或获取图例的标签。

**语法:**

*   设置*标签*属性:

    ```html
    $('#jqxTreeMap').jqxTreeMap({ legendLabel: "TreeMap" });  
    ```

*   要获取 *legendLabel* 属性:

    ```html
    var legendLabel = $('#jqxTreeMap').jqxTreeMap('legendLabel'); 
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxtool tip . js”>

**示例:**下面的示例说明了 jQWidgets jqxtremap**legendLabel**T4 属性。在下面的例子中， *legendLabel* 属性的值被设置为“树形图”。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxtooltip.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxtreemap.js">
    </script>
    <script type="text/javascript" 
            src="scripts/gettheme.js">
    </script>
    <script type="text/javascript" 
            src="scripts/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxTreeMap legendLabel Property
        </h3>
        <div id="Tree_Map"></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_legendLabel" 
               value="Value of the legendLabel property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                var Data_of_TreeMap = [{
                    label: 'GeeksforGeeks',
                    value: 70,
                    color: '#ff0300'
                }, {
                    label: 'is a',
                    value: 10,
                    parent: 'GeeksforGeeks',
                    color: '#ff5400'
                }, {
                    label: 'Computer Science',
                    value: 30,
                    parent: 'GeeksforGeeks',
                    color: '#008000'
                }, {
                    label: 'Portal.',
                    value: 15,
                    parent: 'GeeksforGeeks',
                    color: '#7fbf00'
                }
                ];
                $('#Tree_Map').jqxTreeMap({
                    width: 390,
                    height: 200,
                    source: Data_of_TreeMap,
                    colorMode: 'autoColors',
                    legendLabel: "TreeMap"
                });
                $("#button_for_legendLabel").jqxButton({
                    width: 250
                });
                $("#button_for_legendLabel").click(
                    function () {
                        var legendLabel_Value = 
                            $('#Tree_Map').
                            jqxTreeMap('legendLabel');
                        $("#log").html((
                          legendLabel_Value));
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/0bab6c3a09e3a53e99425a912f3bf55c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtreemap/jquery-tree map-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtreemap/jquery-treemap-api.htm)