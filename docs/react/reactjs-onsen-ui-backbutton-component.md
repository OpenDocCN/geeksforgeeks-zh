# 重新启动用户界面后台按钮组件

> 原文:[https://www . geesforgeks . org/reactjs-onsen-ui-back button-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-backbutton-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。后退按钮组件允许用户在您的应用程序中显示后退按钮。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 反向按钮组件。

**后退按钮道具:**

*   **修饰词:**用于按钮的外观。
*   **onClick:** 是点击按钮时触发的回调函数。

**预设修改器:**

*   **材质:**用于展示材质设计风格。

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
import { Toolbar, BackButton } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI BackButton Component</h6>
      <Toolbar modifier="material" >
        <div className="left">
          <BackButton modifier="material"></BackButton></div>
        <div className="center">Sample Content</div>
      </Toolbar>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/9de36093eb81d7a6ff1db463ff0c06bc.png)****

******参考:**T2】https://onsen.io/v2/api/react/BackButton.html****