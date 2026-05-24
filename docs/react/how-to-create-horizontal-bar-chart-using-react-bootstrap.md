# 如何使用 React Bootstrap 创建横条图？

> 原文:[https://www . geeksforgeeks . org/如何创建-水平条形图-使用-反应-引导/](https://www.geeksforgeeks.org/how-to-create-horizontal-bar-chart-using-react-bootstrap/)

条形图将分类数据和相应的数据值表示为矩形条。通常，x 轴代表分类值，y 轴代表数据值或频率。这叫做垂直条形图，相反的叫做水平条形图。在某些情况下，水平条形图提供更好的可读性。

**创建反应应用程序并安装模块:**

*   **步骤 1:** 使用以下命令创建一个 React 应用程序。

    ```jsx
    npx create-react-app foldername
    ```

*   **步骤 2:** 创建项目文件夹(即文件夹名)后，使用以下命令移动到该文件夹。

    ```jsx
    cd foldername
    ```

*   **步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的模块。

    ```jsx
    npm install --save mdbreact react-chartjs-2
    ```

*   **第四步:**在 index.js 中添加 Bootstrap CSS 和 fontawesome CSS。

    ```jsx
    import '@fortawesome/fontawesome-free/css/all.min.css';  
    import 'bootstrap-css-only/css/bootstrap.min.css';  
    import 'mdbreact/dist/css/mdb.css';
    ```

**项目结构:**如下图。

![](img/11262ae91d9f02e04a2c8c607b7dfb64.png)

项目结构

**示例:**现在在 App.js 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import { MDBContainer } from "mdbreact";
import { HorizontalBar } from "react-chartjs-2";

const App = () => {

  // Sample data
  const data = {
    labels: ["Sunday", "Monday", "Tuesday",
      "Wednesday", "Thursday", "Friday", "Saturday"],
    datasets: [
      {
        label: "Hours Studied in Geeksforgeeks",
        data: [2, 5, 7, 9, 7, 6, 4],
        fill: true,
        backgroundColor: "rgba(6, 156,51, .3)",
        borderColor: "#02b844",
      }
    ]
  }

  return (
    <MDBContainer>
      <HorizontalBar data={data} />
    </MDBContainer>
  );
}

export default App;
```

**运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:

```jsx
npm start
```

**输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

![](img/c390cb54d21b38ca14b7b0cd6cf47e59.png)

输出