# 反应套件分隔器组件

> 原文:[https://www . geesforgeks . org/react-suite-divider-component/](https://www.geeksforgeeks.org/react-suite-divider-component/)

React Suite 是一个流行的前端库，包含一组为中间平台和后端产品设计的 React 组件。分割线  组件允许用户显示分割线。我们可以在 ReactJS 中使用以下方法来使用 React Suite 除法器组件。

**分隔道具:**

*   **儿童:**用于 s et 分割线内的文字。
*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **垂直:**用来表示垂直的分界线。

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
import { Divider } from 'rsuite'

export default function App() {

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React Suite Divider Component</h4>
      <div>
        <h6>Sample content above Divider</h6>
        <Divider />
        <h6>Sample content below Divider</h6>
      </div>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/d27b9014820005c5b1da9e942b44fed8.png)****

******参考:**T2】https://rsuitejs.com/components/divider/****