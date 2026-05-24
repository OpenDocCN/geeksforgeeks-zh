# 反应套件步骤组件

> 原文:[https://www.geeksforgeeks.org/react-suite-steps-component/](https://www.geeksforgeeks.org/react-suite-steps-component/)

React Suite 是一个流行的前端库，包含一组为中间平台和后端产品设计的 React 组件。步骤  组件  指导用户完成一个任务的步骤。它是一种导航条。我们可以在 ReactJS 中使用以下方法来使用 React Suite 步骤组件。

**脚步道具:**

*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **当前:**用于表示当前的执行步骤。
*   **当前状态:**表示当前执行步骤状态。
*   **小:**用于小尺寸踏步栏。
*   **垂直:**用于垂直显示。

**步数。物品道具:**

*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **描述:**用于表示步骤项的描述。
*   **图标:**用于设置图标。
*   **状态:**用于表示步进状态。
*   **标题:**用于表示 Steps 项的标题。

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
import { Steps } from 'rsuite';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React Suite Steps Component</h4>
      <Steps current={1}>
        <Steps.Item />
        <Steps.Item />
        <Steps.Item />
        <Steps.Item />
      </Steps>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/1fe9f85fa6845eb06630d201986d0923.png)****

******参考:**T2】https://rsuitejs.com/components/steps/****