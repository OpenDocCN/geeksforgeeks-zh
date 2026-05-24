# 反应套件徽章组件

> 原文:[https://www.geeksforgeeks.org/react-suite-badge-component/](https://www.geeksforgeeks.org/react-suite-badge-component/)

React Suite 是一个流行的前端库，包含一组为中间平台和后端产品设计的 React 组件。徽章  组件允许用户 在其子组件 的右上角生成一个小徽章。我们可以在 ReactJS 中使用以下方法来使用 React 套件徽章组件。

**徽章道具:**

*   **children:** 用于表示组件的 children。
*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **内容:**表示内容信息。
*   **最大计数:**用于表示最大计数数。

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
import { Badge, Button } from 'rsuite';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 600, paddingLeft: 30
    }}>
      <h4>React Suite Badge Component</h4>
      <br></br>
      <Badge content="NEW">
        <Button>Messages</Button>
      </Badge>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/a8c3f4187ba4d95302217af10d713261.png)****

******参考:**T2】https://rsuitejs.com/components/badge/****