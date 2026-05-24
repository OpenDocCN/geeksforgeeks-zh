# easy ui jquery combogrid widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery-combogrid 小部件/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery EasyUI 设计一个组合网格。 combogrid 将可编辑文本框与下拉数据网格面板相结合，用户可以从中快速查找和选择。

**jQuery 易 UI 下载:**

```html
https://www.jeasyui.com/download/index.php
```

**语法:**

```html
<input class="easyui-combogrid">
```

**属性:**

*   **loadMsg:**data grid 加载远程数据时显示的消息。
*   **id field:**id 字段名。
*   **文本字段:**要在文本框中显示的文本字段。
*   **模式:**定义文本改变时如何加载数据网格数据。
*   **过滤器:**定义当“模式”设置为“本地”时，如何选择本地数据。

**方法:**

*   **选项:**返回选项对象。
*   **网格:**返回 datagrid 对象。
*   **设置值:**设置组件值。
*   **设置值:**设置组件值数组。
*   **清除:**清除组件值。

**进场:**

*   首先，添加项目所需的 jQuery Easy UI 脚本。

> < link rel= "样式表" type="text/css "
> 
> href = " https://www . jeas yui . com/easy ui/themes/default/easy ui . CSS " >
> 
> < link rel= "样式表" type="text/css "
> 
> href = " https://www . jeasyui . com/easyui/themes/icon . CSS " >
> 
> < script type="text/javascript "
> 
> src = " https://www . jeas yui . com/easy ui/jquery . min . js >
> 
> < script type="text/javascript "
> 
> src = " https://www . jeas yui . com/easy ui/jquery . easy ui . min . js >

**示例:**

## 超文本标记语言

```html
<html>
<head>    
    <link rel="stylesheet" type="text/css" 
        href="https://www.jeasyui.com/easyui/themes/default/easyui.css">

    <link rel="stylesheet" type="text/css" 
        href="https://www.jeasyui.com/easyui/themes/icon.css">

    <script type="text/javascript" 
        src="https://www.jeasyui.com/easyui/jquery.min.js"></script>

    <script type="text/javascript" 
        src="https://www.jeasyui.com/easyui/jquery.easyui.min.js"></script>
</head>

<body>
    <div style="margin-bottom:20px">
            <select class="easyui-combogrid" style="width:100%" data-options="
                    panelWidth: 500,
                    idField: 'itemid',
                    textField: 'productname',
                    method: 'get',
                    columns: [[
                        {field:'itemid',title:'Item ID',width:80},
                        {field:'productname',title:'Product',width:120},
                        {field:'listprice',title:'List Price',
                            width:80,align:'right'},
                        {field:'unitcost',title:'Unit Cost',
                            width:80,align:'right'},
                        {field:'attr1',title:'Attribute',width:200},
                        {field:'status',title:'Status',
                            width:60,align:'center'}
                    ]],
                    fitColumns: true,
                    label: 'Select Item:',
                    labelPosition: 'top'
                ">
            </select>
        </div>
</body>

</html>
```

**输出:**

![](img/1cabefb49a22ffd2947b056da97fcf94.png)

**参考:**T2】http://www.jeasyui.com/documentation/