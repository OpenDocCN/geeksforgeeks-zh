# 反应套件零件图组件

> 原文:[https://www . geesforgeks . org/react-suite-pie chart-component/](https://www.geeksforgeeks.org/react-suite-piechart-component/)

React Suite Charts 是一个流行的前端库，包含一组 React 组件，用于提供一组基于 rsuite 和 echarts 的图表。饼图  组件允许用户 p 提供饼图。我们可以在 ReactJS 中使用以下方法来使用 React Suite PieChart 组件。

**英尺图建议:**

*   **名称:**用于表示图形的名称。
*   **数据:**用于传递图形的数据。
*   **起始角度:**用于表示起始角度。
*   **图例:**表示图表是否启用图例。

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
import { PieChart } from '@rsuite/charts';

export default function App() {

  // Sample data
  const sampleData = [
    ['Books', 30],
    ['Cars', 40],
    ['Table', 30],
  ];

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React-Suite Charts PieChart Component</h4>
      <PieChart name="PieChart" data={sampleData} />
    </div >
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/67738f0a9f40f0c169feb569c0c1c5af.png)****

******参考:**T2】https://charts.rsuitejs.com/****