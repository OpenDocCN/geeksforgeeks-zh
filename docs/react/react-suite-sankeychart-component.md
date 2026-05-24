# 反应套件 SankeyChart 组件

> 原文:[https://www . geesforgeks . org/react-suite-sankey chart-component/](https://www.geeksforgeeks.org/react-suite-sankeychart-component/)

React Suite Charts 是一个流行的前端库，包含一组 React 组件，用于提供一组基于 rsuite 和 echarts 的图表。SankeyChart 组件允许用户以链接的形式提供数据。我们可以在 ReactJS 中使用以下方法来使用 React Suite SankeyChart 组件。

**关键词标的物**

*   **名称:**用于表示图形的名称。
*   **数据:**用于传递图形的数据。
*   **高度:**用于表示图形高度。

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
    **npm install @rsuite/charts**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import 'rsuite/dist/styles/rsuite-default.css';
import { SankeyChart } from '@rsuite/charts';
import 'echarts'

export default function App() {

  // Sample data
  const sampleData = {
    nodes: [
      { name: 'Liquid' },
      { name: 'Solid' },
      { name: 'Gas' },
    ],
    links: [
      { source: 'Liquid', target: 'Solid', value: 10 },
      { source: 'Liquid', target: 'Solid', value: 20 },
      { source: 'Gas', target: 'Liquid', value: 40 },
      { source: 'Gas', target: 'Liquid', value: 70 },
    ]
  };

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React-Suite Charts SankeyChart Component</h4>
      <SankeyChart height={300} name="SankeyChart" data={sampleData} />
    </div >
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/5a6ae59f86d373ba335a37bad6adf3a2.png)****

******参考:**T2】https://charts.rsuitejs.com/#%E6%A1%91%E5%9F%BA%E5%9B%BE****