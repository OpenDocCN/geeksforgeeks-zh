# 重新获取蓝图树组件

> 原文:[https://www . geesforgeks . org/reactjs-蓝图-树-组件/](https://www.geeksforgeeks.org/reactjs-blueprint-tree-component/)

是一个基于反应的网络用户界面工具包。该库非常适合构建桌面应用程序的复杂数据密集型界面，并且非常受欢迎。树组件为用户提供了一种显示树结构数据的方式。它用于显示分层数据。我们可以在 reatjs 中使用以下方法来使用 reatjs 蓝图树组件。

**树木道具:**

*   **类名:**用于表示传递给子元素的以空格分隔的类名列表。
*   **内容:**用于表示指定树的内容和外观的数据。
*   **onNodeClick:** 它是一个回调函数，当在插入符号以外的任何地方单击节点以展开/折叠节点时，会触发该函数。
*   **onNodeCollapse:** 是一个回调函数，当点击扩展节点的插入符号时触发。
*   **onNodeContextMenu:** 它是一个回调函数，当右键单击一个节点或在一个焦点节点上按下上下文菜单按钮时触发。
*   **onnodeddoubleclick:**是双击节点时触发的回调函数。
*   **onNodeExpand:** 是一个回调函数，当单击折叠节点的插入符号时触发。
*   **onNodeMouseEnter:** 它是一个回调函数，当鼠标移动到一个节点上时触发。
*   **onNodeMouseLeave:** 是鼠标移出节点时触发的回调函数。

**TreeNode Props:**

*   **子节点:**用于表示该节点的子树节点。
*   **children:** 用来表示 children 元素。
*   **类名:**用于表示传递给子元素的以空格分隔的类名列表。
*   **contentRef:** 用于表示内容 Ref 元素。
*   **深度:**用来表示节点的深度。
*   **禁用:**表示该树节点是否非交互。
*   **hasCaret:** 用于指示是否显示展开/折叠节点的插入符号。
*   **图标:**用于表示节点标签旁边要渲染的图标或图标元素的名称。
*   **id:** 用于表示节点的唯一标识符。
*   **isExpanded:** 继承自*itrenode . isExpanded*属性。
*   **选择:**表示是否选择该节点。
*   **键:**用于表示唯一的键属性。
*   **标签:**用于表示节点的主标签。
*   **节点数据:**用于表示与节点关联的可选自定义用户对象。
*   **onClick:** 是点击 TreeNode 时触发的回调函数。
*   **肿瘤失效:**这是一个回调函数，在树节点崩溃时触发。
*   **onContextMenu:** 它是一个回调函数，当右键单击树节点或按下聚焦树节点上的上下文菜单按钮时触发。
*   **onDoubleClick:** 是用户双击 TreeNode 时触发的回调函数。
*   **onExpand:** 是一个回调函数，在 TreeNode 展开时触发。
*   **onMouseEnter:** 是鼠标进入 TreeNode 时触发的回调函数。
*   **onMouseLeave:** 是鼠标离开 TreeNode 时触发的回调函数。
*   **路径:**用于表示树节点的路径属性。
*   **次要标签:**用于表示显示在节点右侧的次要标签/组件。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```jsx
**npm install @blueprintjs/core**
```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例 1:** 现在在 **App.js** 文件中写下以下代码。这里，这里我们演示了应用了图标元素的树组件。****

## ****java 描述语言****

```jsx
**import React from 'react'
import '@blueprintjs/core/lib/css/blueprint.css';
import { Tree, Classes } from "@blueprintjs/core";

function App() {

    // Sample Tree Data
    const sampleData = [
        {
            id: 0,
            hasCaret: true,
            icon: "folder-close",
            label: "Folders"
        },
        {
            id: 1,
            hasCaret: true,
            icon: "user",
            label: "Profile"
        },
        {
            id: 2,
            hasCaret: true,
            icon: "folder-close",
            label: "Documents"
        },
    ];

    return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Blueprint Tree Component</h4>
            <Tree
                contents={sampleData}
                className={Classes.ELEVATION_0}
            />
        </div>
    );
}

export default App;**
```