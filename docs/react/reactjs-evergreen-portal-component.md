# 反应堆常青门户组件

> 原文:[https://www . geeksforgeeks . org/reactjs-evergreen-portal-component/](https://www.geeksforgeeks.org/reactjs-evergreen-portal-component/)

React Evergreen 是一个受欢迎的前端库，它有一组 React 组件来构建漂亮的产品，因为这个库是灵活的、合理的默认值和用户友好的。门户组件为用户提供了一种在当前 DOM 树之外呈现的方式。这是一个简单的实用程序组件，可以帮助你使用常青树门户组件。

**门户道具:**

*   **children:** 用于表示该组件的 children。

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
    **npm install evergreen-ui**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import { Portal, Pane } from 'evergreen-ui'

export default function App() {

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>ReactJS Evergreen Portal Component</h4>
      <Portal>
        <Pane
          position="fixed"
          background="green"
          padding={20}
          right={0}
          bottom={0}
        >Sample Portal Text!
        </Pane>
      </Portal>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/ff8dfb56926aa3d0a6e34fd01aad5095.png)****

******参考:**T2】https://evergreen.segment.com/components/portal****