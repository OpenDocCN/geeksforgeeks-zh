# 重新获取 Onsen UI 底部工具栏组件

> 原文:[https://www . geesforgeks . org/reactjs-onsen-ui-bottom toolbar-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-bottomtoolbar-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。底部工具栏组件用于显示我们应用程序的底部工具栏。它位于窗户的底部。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 底部工具栏组件。

巴特勒工具栏提议:

*   **修改器:**用于指定修改器名称，以指定自定义样式。

**预设修改器:**

*   **透明:**用于使工具栏透明。
*   **对齐:**用于垂直对齐其子元素，也适用于块元素的 flexbox。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个反应应用程序:

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 在创建项目文件夹(即文件夹名**)后，使用以下命令将**移动到该文件夹:

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

    ```jsx
    **npm install onsenui react-onsenui** 
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react';
import 'onsenui/css/onsen-css-components.css';
import { BottomToolbar } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI BottomToolbar Component</h6>
      <BottomToolbar style={{backgroundColor:'lightcoral', padding: 10}} 
      align="center" modifier="flat-material"> Sample Content of the Bottom Toolbar! 
      </BottomToolbar>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/d0ef114da4af52d7fdb9b2b06138cc11.png)****

******参考:**[https://onsen . io/v2/API/reac/bottle toolbar . html](https://onsen.io/v2/api/react/BottomToolbar.html)****