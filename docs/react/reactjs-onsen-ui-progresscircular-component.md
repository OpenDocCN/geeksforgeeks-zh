# 重新获取 Onsen UI 进程循环组件

> 原文:[https://www . geeksforgeeks . org/reactjs-onsen-ui-progress circular-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-progresscircular-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。进度循环组件是用来显示一个循环进度指示器。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI ProgressCircular 组件。

**进度循环道具:**

*   **修饰符:**用于进度指示器的出现。
*   **值:**用于表示当前进度的值。
*   **次要值:**用于表示当前次要进度的值。
*   **中间:**如果设置为真，用于显示无限循环动画。

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
import { ProgressCircular } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI ProgressCircular Component</h6>
      <ProgressCircular modifier="material" value={100} /> <br></br>
      <ProgressCircular indeterminate />
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/552af54a187d73657139512885d441aa.png)****

******参考:**T2】https://onsen.io/v2/api/react/ProgressCircular.html****