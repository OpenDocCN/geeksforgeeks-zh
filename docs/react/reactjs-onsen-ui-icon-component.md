# 重新获取 Onsen 用户界面图标组件

> 原文:[https://www . geesforgeks . org/reactjs-onsen-ui-icon-component/](https://www.geeksforgeeks.org/reactjs-onsen-ui-icon-component/)

ReactJS Onsen-UI 是一个受欢迎的前端库，具有一组 React 组件，旨在以一种美观高效的方式开发 HTML5 混合和移动网络应用程序。图标 c 组件是用于显示图标，因为图标是每个用户界面应用程序所必需的。我们可以在 ReactJS 中使用以下方法来使用 Onsen-UI 图标组件。

**图标道具:**

*   **修改器:**用于图标的外观。
*   **图标:**用于指定像*离子-导航图标、*等图标。
*   **大小:**用于以像素为单位表示图标大小。
*   **旋转:**用于表示旋转图标的度数。
*   **fixed with:**用于定义图标在列表中使用时的 fixed with。
*   **旋转:**用于指定图标是否应该旋转。

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
import { Icon } from 'react-onsenui';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 500, paddingLeft: 30
    }}>
      <h6>ReactJS Onsen-UI Icon Component</h6>
      <Icon icon='fa-twitter'
        size={26}
        style={{ verticalAlign: 'middle' }}
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

****![](img/18eb604a5971d23f309451d1acae0de0.png)****

******参考:**T2】https://onsen.io/v2/api/react/Icon.html****