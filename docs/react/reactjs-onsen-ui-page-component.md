# 重新获取 Onsen UI 页面组件

> 原文:[https://www . geeksforgeeks . org/reactjs-onsen-ui-page-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-page-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。页面组件用于处理整个页面。内容可以滚动。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 页面组件。

**页面命题:**

*   **contentStyle:** 用于指定页面内容的样式。
*   **修改器:**用于指定修改器名称，以指定自定义样式。
*   **renderModal:** 是一个回调函数，用来渲染一个遮挡当前屏幕的模态。
*   **渲染工具栏:**是一个回调函数，用于渲染页面的工具栏。
*   **renderBottomToolbar:** 是一个回调函数，用于渲染页面的底部工具栏。
*   **renderFixed:** 是一个回调函数，用于渲染页面的固定内容。
*   **onInit:** 是一个回调函数，在页面附加后立即触发。
*   **onShow:** 是页面显示后立即触发的回调函数。
*   **onHide:** 是页面隐藏后触发的回调函数。
*   **oninfonitescroll:**是滚动到页面底部时触发的回调函数。
*   **onDeviceBackButton:** 用作设备后退按钮的自定义处理程序。

**预设修改器:**

*   **材质:**用于展示材质设计。

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
import 'onsenui/css/onsenui.css';
import { Page } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI Page Component</h6>
      <Page style={{ width: 400, height: 200, position: 'relative' }}>
        <div>I am sample Page Content</div>
      </Page>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/e8b4c7025064acffb05e21b3f7592592.png)****

******参考:**[https://onsen . io/v2/API/reac/page . html](https://onsen.io/v2/api/react/Page.html)****