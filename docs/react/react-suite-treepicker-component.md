# 反应套件树选择器组件

> 原文:[https://www . geesforgeks . org/react-suite-tree picker-component/](https://www.geeksforgeeks.org/react-suite-treepicker-component/)

React Suite 是一个流行的前端库，包含一组为中间平台和后端产品设计的 React 组件。TreePicker 组件允许用户提供一个单一的树选择器。用户可以从下拉列表中选择一个树层次结构形式的值。  我们可以在 ReactJS 中使用以下方法来使用 React Suite TreePicker 组件。

**TreePicker 提议:**

*   **外观:**用于组件外观。
*   **块:**用于块整行。
*   **childrenKey:** 用于表示 Tree 数据结构 Children 属性名称。
*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **可清洗:**用于指示选项是否可以清空。
*   **容器:**用于设置渲染容器。
*   **数据:**用于表示可选数据。
*   **defaultexpandal:**默认用于扩展所有节点。
*   **defaultExpandItemValues:** 用于设置默认扩展节点的值。
*   **默认打开:** 用于默认打开。
*   **默认值:**用于表示默认值。
*   **禁用:**表示组件是否禁用。
*   **disableItemValues:**用于禁用可选。
*   **expandItemValues:** 用于设置扩展节点(受控)的值。
*   **高度:**用于表示菜单高度。
*   **标签页:**用于设置显示“数据”中“键”的选项。
*   **菜单项名称:**用于表示应用于菜单 DOM 节点的 CSS 类。
*   **菜单样式:**用于表示应用于菜单 DOM 节点的样式。
*   **onChange:** 是一个回调函数，当值发生变化时触发。
*   **onClean:** 是值清空时触发的回调函数。
*   **onClose:** 是关闭事件触发的回调函数。
*   **onEnter:** 是一个回调函数，在叠加转换之前触发。
*   **OneHinded:**这是一个回调函数，在覆盖完成转换后触发。
*   **OnLining:**这是一个回调函数，当覆盖开始转换时被触发。
*   **onExit:** 它是一个回调函数，在覆盖转换之前被触发。
*   **onexitted:**是一个回调函数，在覆盖完成转换后触发。
*   **onExiting:** 是一个回调函数，在叠加开始向外过渡时触发。
*   **onExpand:** 是显示树节点时触发的回调函数。
*   **onOpen:** 是组件打开时触发的回调函数。
*   **onSearch:** 是搜索的回调函数。
*   **onSelect:** 是一个回调函数，在选择一个选项时触发。
*   **open:** 是在 open 事件(受控)上触发的回调函数。
*   **占位符:**用于表示占位符。
*   **放置:**用于元件的放置。
*   **渲染额外页脚:**用于自定义渲染额外页脚。
*   **渲染树图标:**用于表示自定义渲染图标。
*   **渲染树节点:**用于表示自定义渲染树节点。
*   **渲染值:**用于自定义渲染选定选项。
*   **搜索依据:**用于自定义搜索规则。
*   **可搜索:**用于表示是否可以搜索选项。
*   **尺寸:**用于表示采摘器尺寸。
*   **toggleComponentClass:** 可用于该组件的自定义元素。
*   **值:**用于表示值(受控)。
*   **valueKey:** 用于设置“数据”中的选项值‘key’。
*   **虚拟化:**表示是否使用虚拟化列表。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

    ```jsx
    **npm install rsuite**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import 'rsuite/dist/styles/rsuite-default.css';
import { TreePicker } from 'rsuite';

export default function App() {

  // Sample Options
  const options = [
    {
      "label": "Madhya Pradesh",
      "value": 1,
      "children": [
        {
          "label": "Mhow",
          "value": 2
        },
        {
          "label": "Indore",
          "value": 3,
          "children": [
            {
              "label": "Vijay Nagar",
              "value": 4
            },
            {
              "label": "Rajiv Gandhi Square",
              "value": 5
            },
            {
              "label": "MR 10",
              "value": 6
            },
          ]
        },
      ]
    }
  ]

  return (
    <div style={{
      display: 'block', width: 600, paddingLeft: 30
    }}>
      <h4>React Suite TreePicker Component</h4>
      <TreePicker
        style={{ width: 300 }}
        defaultExpandAll
        placeholder="Select your Nearest Office"
        data={options}
      />
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/b9aa8e15b44db0436eda79d32eed1387.png)****

******参考:**T2】https://rsuitejs.com/components/tree-picker/****