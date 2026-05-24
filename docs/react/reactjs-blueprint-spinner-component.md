# 反应堆蓝图旋转器组件

> 原文:[https://www . geesforgeks . org/reactjs-蓝图-spinner-component/](https://www.geeksforgeeks.org/reactjs-blueprint-spinner-component/)

是一个基于反应的网络用户界面工具包。该库非常适合构建桌面应用程序的复杂数据密集型界面，并且非常受欢迎。微调器组件为用户提供了一种循环显示进度的方式。  我们可以在 ReactJS 中使用以下方法来使用 ReactJS 蓝图微调器组件。

**旋转道具:**

*   **类名:**用于表示传递给子元素的以空格分隔的类名列表。
*   **意图:**用于表示应用于元素的视觉意图颜色。
*   **大小:**用于以像素为单位表示微调器的大小。
*   **标记名:**用于表示两个包装元素的 HTML 标记。
*   **值:**用于表示 0 到 1(包括 0 和 1)之间的值，表示操作的进度。

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
    **npm install @blueprintjs/core**
    ```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例:**现在在 **App.js** 文件中写下以下代码。在这里，App 是我们编写代码的默认组件。****

## ****App.js****

```jsx
**import React from 'react'
import '@blueprintjs/core/lib/css/blueprint.css';
import { Spinner } from "@blueprintjs/core";

function App() {

    return (
        <div style={{
            display: 'block', width: 500, padding: 30
        }}>
            <h4>ReactJS Blueprint Spinner Component</h4>
            <Spinner size={10} /> <br></br><br></br>
            <Spinner size={20} /> <br></br><br></br>
            <Spinner size={30} /> <br></br><br></br>
        </div>
    );
}

export default App;**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/d2cf241a762c534636ec0fc00e6bc026.png)****

******参考:**T2】https://blueprintjs.com/docs/#core/components/spinner****