# 反应套件导航条组件

> 原文:[https://www.geeksforgeeks.org/react-suite-navbar-component/](https://www.geeksforgeeks.org/react-suite-navbar-component/)

React Suite 是一个流行的前端库，包含一组为中间平台和后端产品设计的 React 组件。导航栏  组件允许用户在页面顶部提供导航。  我们可以在 ReactJS 中使用以下方法来使用 React Suite Navbar 组件。

**Navbar Props:**

*   **外观:**用于导航栏外观。
*   **类前缀:**用于表示组件 CSS 类的前缀。
*   **componentClass:** 可用于该组件的自定义元素类型。

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
import { Navbar, Nav, Dropdown } from 'rsuite';

export default function App() {

  return (
    <div style={{
      display: 'block', width: 700, paddingLeft: 30
    }}>
      <h4>React Suite Nav Component</h4>
      <Navbar>
        <Navbar.Header>
          <a href="/home" className="navbar-brand logo">
           CompanyName
          </a>
        </Navbar.Header>
        <Navbar.Body>
          <Nav>
            <Nav.Item>Login</Nav.Item>
            <Nav.Item>Signup</Nav.Item>
            <Dropdown title="Features">
              <Dropdown.Item>Settings</Dropdown.Item>
              <Dropdown.Item>About</Dropdown.Item>
            </Dropdown>
          </Nav>
        </Navbar.Body>
      </Navbar>
    </div>
  );
}**
```

******运行应用程序的步骤:**从项目的根目录使用以下命令运行应用程序:****

```jsx
**npm start**
```

******输出:**现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:****

****![](img/b33b0eb1bd46bb31d857685e834eab1b.png)****

******参考:**T2】https://rsuitejs.com/components/navbar/****