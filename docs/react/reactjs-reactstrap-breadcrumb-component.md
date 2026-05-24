# 反应捕捉面包屑组件

> 原文:[https://www . geeksforgeeks . org/reactjs-reatstrap-bread-component/](https://www.geeksforgeeks.org/reactjs-reactstrap-breadcrumb-component/)

Reactstrap 是一个流行的前端库，易于使用 React Bootstrap 4 组件。该库包含引导 4 的无状态反应组件。面包屑组件提供了一种指示当前页面位置的方式。我们可以在 ReactJS 中使用以下方法来使用 ReactJS Reactstrap 面包屑组件。

**面包屑道具:**

*   **标签:**用于表示该组件的标签。
*   **列表标签:**用于表示 ol、ul 等列表标签。
*   **类名:**用于表示面包屑组件的类名。
*   **列表类名:**用于表示列表样式的类名。
*   **cssModule:** 用来表示造型用的 CSS 模块。
*   **children:** 用于将 children 元素传递给这个组件。
*   **咏叹调标签:**用于表示咏叹调标签属性。

**面包屑道具:**

*   **标签:**用于表示该组件的标签。
*   **激活:**用于表示物品是否处于激活状态。
*   **类名:**用于表示造型的类名。
*   **cssModule:** 用来表示造型用的 CSS 模块。

**创建反应应用程序并安装模块:**

**步骤 1:** 使用以下命令创建一个反应应用程序:

```jsx
npx create-react-app foldername
```

**步骤 2:** 创建项目文件夹(即文件夹名**)后，使用以下命令移动到该文件夹中:**

```jsx
cd foldername
```

**步骤 3:** 创建 ReactJS 应用程序后，使用以下命令安装所需的****模块:****

```jsx
**npm install reactstrap bootstrap**
```

******项目结构:**如下图。****

****![](img/f04ae0d8b722a9fff0bd9bd138b29c23.png)

项目结构**** 

******示例 1:** 现在在 **App.js** 文件中写下以下代码。在这里，我们已经使用了活动和 href 道具的面包屑组件。****

## ****java 描述语言****

```jsx
**import React from 'react'
import 'bootstrap/dist/css/bootstrap.min.css';
import { Breadcrumb, BreadcrumbItem } from "reactstrap"

function App() {
    return (
        <div style={{
            display: 'block', width: 700, padding: 30
        }}>
            <h4>ReactJS Reactstrap Breadcrumb Component</h4>
            <Breadcrumb>
                <BreadcrumbItem><a href="#">Dashboard</a></BreadcrumbItem>
                <BreadcrumbItem active>Profile</BreadcrumbItem>
            </Breadcrumb>
            <Breadcrumb>
                <BreadcrumbItem><a href="#">Logout</a></BreadcrumbItem>
                <BreadcrumbItem><a href="#">Settings</a></BreadcrumbItem>
            </Breadcrumb>
        </div>
    );
}

export default App;**
```