# EasyUI jQuery TreeGrid Widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery-tree grid 小部件/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery EasyUI 设计 treegrid。树形网格用于显示网格中的分层数据。

## jQuery EasyUI 下载

```html
https://www.jeasyui.com/download/index.php
```

## 语法

```html
<input class="easyui-treegrid">
```

## 属性

*   `idField`: 表示哪个字段是标识字段。
*   `treeField`: 定义树节点字段。
*   `animate`: 定义当节点展开或折叠时是否显示动画效果。
*   `checkbox`: 定义是否在每个行节点前显示复选框。
*   `cascadeCheck`: 定义是否级联检查。
*   `onlyLeafCheck`: 定义是否仅在叶节点前显示复选框。
*   `lines`: 定义是否显示树网格节点之间的线条。
*   `loader`: 如何从远程服务器加载数据。返回`false`可以中止这个动作。
*   `loadFilter`: 返回过滤后的数据进行显示。

## 事件

*   `onLoadSuccess`: 数据加载成功时触发。
*   `onLoadError`: 在加载远程数据时出现一些错误时触发。
*   `onBeforeLoad`: 在请求加载数据之前被激发。
*   `onClickRow`: 当用户单击一行时会触发，参数包含。
*   `onDblClickRow`: 当用户双击一行时会触发，参数包含。
*   `onClickCell`: 当用户点击一个单元格时就会被触发。
*   `onDblClickCell`: 当用户双击一个单元格时会被激发。
*   `onBeforeSelect`: 在用户选择一行之前触发。
*   `onSelect`: 当用户选择一行时，它将被激发。
*   `onBeforeUnselect`: 在用户取消选择行之前触发。
*   `onUnselect`: 当用户取消选择一行时，它将被触发。
*   `onBeforeCheckNode`: 它在用户检查一行之前被激发。
*   `onCheckNode`: 当用户检查一行时，它被激发。
*   `onBeforeExpand`: 在一行展开之前被解雇。
*   `onExpand`: 在行扩展时被触发。
*   `onBeforeCollapse`: 它在一行被折叠之前被触发。
*   `onCollapse`: 当一行被折叠时，它会被触发。
*   `onContextMenu`: 右键单击一行时会触发。
*   `onBeforeEdit`: 当用户开始编辑一行时，它会被激发。
*   `onAfterEdit`: 当用户完成编辑时，它会被触发。
*   `onCancelEdit`: 当用户取消编辑一行时，它会被触发。

## 方法

*   `options()`: 返回树网格的选项。
*   `resize()`: 设置树网格大小。
*   `fixRowHeight()`: 固定指定行高。
*   `loadData()`: 加载树网格数据。
*   `load()`: 加载并显示第一页。
*   `reload()`: 它重载 treegrid 数据。
*   `reloadFooter()`: 重新加载页脚数据。
*   `getData()`: 获取加载的数据。
*   `getFooterRows()`: 获取页脚数据。
*   `getRoot()`: 获取根节点，返回节点对象。
*   `getRoots()`: 它获取根节点，返回节点数组。
*   `getParent()`: 它获取父节点。
*   `getChildren()`: 获取子节点。
*   `getSelected()`: 获取选定的节点并返回，如果没有选定的节点返回空值。
*   `getSelections()`: 获取所有选中的节点。
*   `getCheckedNodes()`: 它获取所有选中的行。
*   `getLevel()`: 获取指定的节点级别。
*   `find()`: 查找指定节点，返回节点数据。
*   `select()`: 选择一个节点。
*   `unselect()`: 取消选择一个节点。
*   `selectAll()`: 选择所有节点。
*   `unselectAll()`: 它取消选择所有节点。
*   `checkNode()`: 设置要检查的指定行节点。
*   `uncheckNode()`: 将指定的行节点设置为取消选中。
*   `collapse()`: 它折叠一个节点。
*   `expand()`: 它展开一个节点。
*   `collapseAll()`: 它折叠所有节点。
*   `expandAll()`: 扩展所有节点。
*   `expandTo()`: 从根节点扩展到指定节点。
*   `toggle()`: 切换节点的展开/折叠状态。
*   `append()`: 它将节点追加到父节点。
*   `remove()`: 移除一个节点及其子节点。
*   `pop()`: 弹出，移除该节点后返回包含其子节点的节点数据。
*   `refresh()`: 刷新指定节点。
*   `update()`: 更新指定节点。
*   `beginEdit()`: 开始编辑节点。
*   `endEdit()`: 结束编辑节点。
*   `cancelEdit()`: 取消编辑节点。
*   `getEditors()`: 获取指定的行编辑器。
*   `getEditor()`: 获取指定的编辑器。
*   `showLines()`: 显示树格线。

## 示例

首先，添加项目所需的 jQuery EasyUI 脚本。

```html
<script type="text/javascript" src="jquery.easyui.min.js"></script>
<script type="text/javascript" src="jquery.easyui.mobile.js"></script>
```

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" type="text/css" href="https://www.jeasyui.com/easyui/themes/default/easyui.css">
    <link rel="stylesheet" type="text/css" href="https://www.jeasyui.com/easyui/themes/icon.css">
    <script type="text/javascript" src="https://www.jeasyui.com/easyui/jquery.min.js"></script>
    <script type="text/javascript" src="https://www.jeasyui.com/easyui/jquery.easyui.min.js"></script>
    <script type="text/javascript">
        $(document).ready(function() {
            $('#gfg').treegrid({
                rownumbers: true,
                showFooter: true,
                idField: 'id',
                treeField: 'region',
                animate: true
            });
        });
    </script>
</head>

<body>
    <h2>GeeksforGeeks</h2>
    <p>jQuery EasyUI TreeGrid Widget</p>
    <div style="margin:20px 0;"></div>
    <table id='gfg' title="EasyUI TreeGrid">
        <thead>
            <tr>
                <th colspan="4">Geek1</th>
                <th colspan="4">Geek2</th>
            </tr>
            <tr>
                <th field="1" width="60" align="Center">A</th>
                <th field="2" width="60" align="Center">B</th>
                <th field="3" width="60" align="Center">C</th>
                <th field="4" width="60" align="Center">D</th>
                <th field="5" width="60" align="Center">E</th>
                <th field="6" width="60" align="Center">F</th>
                <th field="7" width="60" align="Center">G</th>
                <th field="8" width="60" align="Center">H</th>
            </tr>
        </thead>
    </table>
</body>

</html>
```

## 输出

![](img/9561a47acfb931a364310ff277dd1b11.png)

树格栅

## 参考

http://www.jeasyui.com/documentation/