# 如何使用材质 UI 和 DevExpress 在 react 中创建散点图？

> 原文:[https://www . geesforgeks . org/如何创建使用材料的反应散点图-ui-and-devexpress/](https://www.geeksforgeeks.org/how-to-create-scatter-chart-in-react-using-material-ui-and-devexpress/)

**DevExpress:** DevExpress 是一个用于控制和构建 Window、Mobile 和其他应用程序的用户界面的包。

**散点图:**散点图是一组虚线点，代表水平轴和垂直轴上的单个数据。两个变量的值沿 X 轴和 Y 轴绘制的图表，结果点的模式揭示了它们之间的相关性。

**创建 React 应用程序和安装模块的步骤:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹即文件夹名称后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的模块。

    ```jsx
    npm i --save @devexpress/dx-react-core @devexpress/dx-react-chart
    npm install @material-ui/core
    npm i --save @devexpress/dx-react-chart-material-ui
    ```

**项目结构:**如下图:

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 App.js 文件中写下以下代码。在这里，应用程序是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import Paper from '@material-ui/core/Paper';
import {
  ArgumentAxis,
  ValueAxis,
  Chart,
  ScatterSeries,
} from '@devexpress/dx-react-chart-material-ui';

const App = () => {

// Sample data
const data = [
  { x: 1, y: 2 },
  { x: 1.2, y: 3 },
  { x: 1.3, y: 5 },
  { x: 1.7, y: 4 },
  { x: 1.9, y: 1 },
  { x: 2, y: 2 },
  { x: 2.3, y: 4 },
  { x: 2.6, y: 3 },
  { x: 2.9, y: 3 },
  { x: 3.2, y: 1 },
  { x: 3.5, y: 5 },
  { x: 3.8, y: 4 },
  { x: 4, y: 5 },
  { x: 4.2, y: 3 },
  { x: 4.4, y: 1 },
];
return (
    <Paper>
    <Chart
      data={data}
    >
      <ArgumentAxis />
      <ValueAxis />

      <ScatterSeries valueField="y" argumentField="x" />
    </Chart>
  </Paper>
);
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/49df7bda4306586aa2027d50553e8324.png)

输出