# 如何使用 React Bootstrap 创建雷达图？

> 原文:[https://www . geesforgeks . org/如何创建雷达图-使用-反应-引导/](https://www.geeksforgeeks.org/how-to-create-radar-chart-using-react-bootstrap/)

雷达图是由一系列等角辐条组成的图表，称为半径，每个辐条代表一个变量。雷达图基本上是以二维图表的形式显示数据的一种图形方法，该图表由三个或更多的定量变量组成，这些变量表示在从同一点开始的轴上。

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

![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构

**示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。

## App.js

```jsx
import React from "react";
import { MDBContainer } from "mdbreact";
import { Radar } from "react-chartjs-2";

const App = () => {

  // Sample data
  const data = {
    labels: ["Sunday", "Monday", "Tuesday", 
    "Wednesday", "Thursday", "Friday", "Saturday"],
    datasets: [
      {
        label: "Hours Studied in Geeksforgeeks",
        data: [8, 5, 6, 7, 5, 3, 8],
        backgroundColor: "rgba(6, 156,51, .3)",
        borderColor: "#02b844",
      }
    ]
  }

  return (
    <MDBContainer>
      <Radar data={data} style={{ maxHeight: '600px' }}/>
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

![](img/8a9001757d38f086de52686af0f70869.png)